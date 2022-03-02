FROM gcc:latest as builder

COPY . /usr/src/c_test

WORKDIR /usr/src/c_test

# RUN gcc -o code_education main.c -static
RUN gcc -O2 -march=native -fwhole-program -ffunction-sections -Wl,--gc-sections -flto main.c -o code_education -static

FROM scratch
COPY --from=builder /usr/src/c_test/code_education code_education
CMD ["./code_education"]
