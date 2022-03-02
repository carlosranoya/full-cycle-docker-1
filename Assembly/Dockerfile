FROM carlosranoya/nasm_x86_64 as builder

COPY . /usr/src/nasm_temp

WORKDIR /usr/src/nasm_temp

RUN /usr/bin/nasm -f elf64 code_education.asm
RUN ld code_education.o -o code_education

FROM scratch

COPY --from=builder /usr/src/nasm_temp/code_education code_education

CMD ["./code_education"]