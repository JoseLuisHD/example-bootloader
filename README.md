# BIOS Bootloader - Hello World (NASM)

This is a simple "Hello World" bootloader written in NASM for BIOS systems. It is intended as a minimal example of how to write and test boot code using the x86 real mode and BIOS interrupts.

---

## 🧠 What is a Bootloader?

A bootloader is a small piece of code executed by the BIOS after powering on the computer. Its main job is to initialize hardware and load the operating system — but in this case, it simply prints a message to the screen.

---

## 📜 What It Does

- Loads at memory address `0x7C00` (standard BIOS boot location).
- Prints the message `"Bootloader working!"` character by character using BIOS interrupt `int 0x10`.
- Enters an infinite loop after displaying the message.

---

## ⚙️ How to Build

Make sure you have [NASM](https://www.nasm.us/) installed.

```bash
nasm -f bin bootloader.asm -o bootloader.bin
```

---

## 🧪 How to Run in QEMU

```bash
qemu-system-x86_64 -drive format=raw,file=bootloader.bin
```