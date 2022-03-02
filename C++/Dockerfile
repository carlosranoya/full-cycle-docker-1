FROM gcc:latest as builder

COPY . /usr/src/cpp_test

WORKDIR /usr/src/cpp_test

RUN g++ -O2 -march=native -fwhole-program -ffunction-sections -Wl,--gc-sections -flto main.cpp -o code_education -static

FROM scratch
COPY --from=builder /usr/src/cpp_test/code_education code_education
CMD ["./code_education"]