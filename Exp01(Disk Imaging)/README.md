# Experiment 1: Disk Imaging
## Aim
To create a forensic bit-by-bit copy (disk image) of a storage device and verify its integrity using MD5 and SHA-256 hash values.

## Theory:
Disk imaging is a fundamental step in digital forensics. It involves creating an exact sector-by-sector copy of a storage device so that the original evidence remains unchanged during analysis.

## Requirements:
- Linux system (Ubuntu/Kali)/FTK Imager
- For FTK Imager ,we mount,preview and image digital evidence(a tool)
- dd or dcfldd
- Root privileges
- Storage device

## Procedure:

### Step 1: Identify the Target Device
```bash
lsblk
sudo fdisk -l
```
Step 2: Create Disk Image
```bash
chmod +x disk_imaging.sh
sudo ./disk_imaging.sh
```
Step 3: Verify Hash Values
```bash
md5sum disk_image.dd
sha256sum disk_image.dd
```
Step 4: Mount the Image (Read-Only)
```bash
sudo mkdir -p /mnt/forensic
sudo mount -o ro,loop disk_image.dd /mnt/forensic
ls /mnt/forensic
sudo umount /mnt/forensic
```
## Result:
A forensic disk image of the selected storage device was successfully created. The hash values of the source and the image were compared and found to be identical, confirming data integrity.

## Conclusion:
This experiment demonstrates that disk imaging is an essential process in digital forensics. By using hashing techniques, the integrity of the acquired data can be verified, ensuring that the evidence remains reliable for further analysis.
