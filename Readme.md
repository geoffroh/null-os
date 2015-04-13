Creates a bootable disk image in assembly.
Following basic steps on http://mikeos.sourceforge.net/write-your-own-os.html

1. compile with nasm:
  ```
  nasm -f bin -o boot.bin boot.asm
  ```
2. write to a virtual floppy:
  ```
  dd conv=notrunc if=boot.bin of=boot.flp
  ```
3. Run with qemu:
  ```
  qemu-system-i386 -fda boot.flp
  ```