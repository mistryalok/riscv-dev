export PATH=/home/alok/prog/gcc_riscv/bin/:$PATH
export RISCV32=/home/alok/prog/gcc_riscv/bin

hello: hello.o link.lds
	$(RISCV32)/riscv32-unknown-elf-ld -T link.lds -o hello hello.o

hello.o: hello.s
	$(RISCV32)/riscv32-unknown-elf-as -o hello.o hello.s

qemu:
	/home/alok/prog/qemu_riscv/bin/qemu-system-riscv32 -machine sifive_u -nographic -kernel hello -bios none -smp 2

clean:
	-rm -f hello hello.o
