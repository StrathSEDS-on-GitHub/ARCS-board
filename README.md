```
make && st-flash write build/ARCS-board.bin 0x8000000
```

```
openocd -f interface/stlink.cfg -f target/stm32g0x.cfg -c "init"
```

```
arm-none-eabi-gdb -ex "target extended-remote :3333" -ex "load build/ARCS-board.elf" -ex "file build/ARCS-board.elf" -ex "monitor arm semihosting enable"
```