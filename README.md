# EmulateOS
USE DEVICE EMULATORS ON ANDROID AND IOS

import subprocess

def start_qemu_emulator(image_path, architecture='arm', memory='256M'):
    # Command to start QEMU emulator
    command = [
        'qemu-system-' + architecture,
        '-m', memory,
        '-drive', 'file=' + image_path,  # Path to the disk image
        '-display', 'gtk'  # Use GTK display
    ]

    # Start the QEMU emulator
    subprocess.run(command)

# Example usage
if __name__ == "__main__":
    # Replace 'path/to/disk_image.img' with the actual path to your disk image file
    disk_image_path = 'path/to/disk_image.img'
    
    # Start QEMU emulator for ARM architecture with 256MB of memory
    start_qemu_emulator(disk_image_path, architecture='arm', memory='256M')

