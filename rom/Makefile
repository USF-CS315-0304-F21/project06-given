HEX_FILES = dp-reg.hex dp-imm.hex dp-lsl-imm.hex dp-lsr-reg.hex dp-asr-imm.hex\
			mem-reg.hex mem-imm.hex mem-shift-reg.hex\
			blbx.hex b.hex beq.hex ble.hex bgt.hex\
			mul.hex rsb.hex\
			quadratic_s.hex get_bitseq_s.hex max3_s.hex fib_rec_s.hex
# TODO			sort_s.hex merge_sort_s.hex

.PRECIOUS: %.o

%.o: %.s
	as -o $@ $<

%.hex: %.o
	objdump -d $< | python3 makerom3.py > $@

all: $(HEX_FILES)

clean:
	rm -rf $(HEX_FILES) *.o
