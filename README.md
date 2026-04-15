

🚩 Troubleshooting Log: The "Invisible" Character Battle
Issue: Repeated "Permission Denied" errors when logging into Bandit Level 1 despite using the correct password string.
Root Causes Identified:
Visual Ambiguity: In terminal monospace fonts, the characters I (Uppercase i), l (Lowercase L), and 1 (Number one) look identical.
Case Sensitivity: A single lowercase f instead of uppercase F at the end of the string caused authentication failure.
PowerShell Formatting: Discovered that pasting into PowerShell can sometimes introduce hidden trailing spaces or newline characters.
Resolution:
Switched to copy-pasting to bypass keyboard layout mapping issues.
Used the Backspace trick after pasting to ensure no hidden whitespace was included.
Verified character case by cross-referencing the cat output from the previous level
Level 2 → Level 3 Reflection
Standard Method: Use quotes ("") or backslashes (\ ) to escape spaces.
The "Genius" Method: Use ls -i to find the inode and find -inum to execute cat.
Why it works: Bypasses shell parsing issues by targeting the file's unique index number rather than its string name. 
