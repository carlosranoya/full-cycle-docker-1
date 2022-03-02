# Full Cycle - Docker

## Deasfio 1

\
A imagem docker solicitada, com a implementação em *Golang* é esta, com 1.16MB:

\
**carlosranoya/codeeducation:0.0.1**



\
Com a intenção e curiosidade de gerar containers menores ainda, fiz tentativas compilando o executável em C++, C e Assembler. Este último deu mais trabalho, porque não encontrei nenhuma imagem no docker oficial com compilador assembler que resolvesse, aí tive que criar uma imagem a partir de um linux que suportasse o montador nasm e que rodasse em máquinas de 64 bits.

Nas versões pra C e C++ descobri que teria que compilar com link estático pra poder funcionar na imagem scratch do Docker, e desta forma as imagens não ficaram tão pequenas quanto eu imaginava. A imagem em C++ ficou maior que a imagem em Go, mesmo com algumas tentativas de otimização de tamanho na compilação e linkagem. Mas as bibliotecas std linkadas estaticamente não têm muito como ser reduzidas em tamanho.


Então as versões seguintes da imagem são estas:

\
*C++* (g++, 1.77MB)\
**carlosranoya/codeeducation:0.0.2**

\
*C* (gcc, 890kB)\
**carlosranoya/codeeducation:0.0.3**

\
*Assembler* (nasm, 8.89kB)\
**carlosranoya/codeeducation:0.0.4**

