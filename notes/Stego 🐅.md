# Investigate image metadata
- Use command `file image.png`
- Use command `exiftool image.png`
- Use command `xxd image.png`
- Use command `strings image.png`
- Use tool binwalk to search binary images for embedded files and executable code: `binwalk image.png`
	- To extract the file: `binwalk -e image.png`
- Use command: `steghide extract -sf image.png`