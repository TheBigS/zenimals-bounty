⸻

🔍 Speculative Write-Up: Possible Path to Custom Zenimals Audio

Hi all,

I’ve been poking around at how the Zenimals SD card system seems to work. I don’t have a device in front of me right now to validate, so please treat this as a working hypothesis rather than a confirmed exploit. If anyone here does have the hardware, I’d love your help testing and filling in the gaps.

⸻

What looks to be happening
• The SD card is FAT16/FAT32.
• Tracks are stored as numbered files (00, 01, etc).
• Each track has a fixed header (likely ~512 bytes), followed by what appears to be raw PCM/WAV audio.
• Stripping the header off lets the file play fine in Audacity/VLC.

⸻

Hypothetical replacement process
1. Backup card with dd.
2. Trim off header, confirm audio plays.
3. Convert your own track into 16-bit PCM WAV (mono, 44.1kHz).
4. Reattach the original header, either by concatenation or overwriting audio after the header block.
5. Copy back and test in device.

⸻

What I need help with

Since I don’t have a Zenimal on hand right now, could anyone:
• Provide raw files from different Zenimal SD cards (multiple tracks if possible).
• Attempt a firmware dump if you’re comfortable opening the device (to check for additional validation).
• Confirm whether the header size is consistent across files or varies.
• Test whether swapped-in audio actually plays, or if there’s hidden checksum/DRM logic.

If someone’s able to validate this approach, I’m happy to clean it up into a toolchain for easier track swapping.

⸻

Note

I don’t currently have a unit to test with. If the bounty requires hardware testing, I’m willing to pick one up — or if someone is willing to comp the cost of a device, I’ll cover the work and documentation side.
⸻
