PACKER ?= packer
ISO ?= ${OEL8_ISO_PATH}

.PHONY: all clean

all: oel8.tar.gz

rhel8.tar.gz: clean
	sudo ${PACKER} init oel8.pkr.hcl && sudo PACKER_LOG=1 ${PACKER} build -var "oel8_iso_path=${ISO}" oel8.pkr.hcl
	reset

clean:
	sudo ${RM} -rf output-qemu oel8.tar.gz
