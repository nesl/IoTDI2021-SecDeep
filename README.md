This is the repo for IoTDI 2021 SecDeep paper.

There are total of 5 components you need to have before you can replicate
the results of SecDeep.

https://github.com/nesl/arm-secure-nn.git
https://github.com/nesl/arm-nn-examples.git
https://github.com/nesl/hikey960-3.5.0.git
https://github.com/nesl/arm-nn-secure-library.git
https://github.com/nesl/llvm-project

Make sure you installed all the required libraries and tools before compiling them.
You have to compile all of them! Or the results will fail. And follow the instructions
on each of the repo to install the compiled libraries. Whenever you recompile
any repo, the whole installation procedures need to be done once again.

Lastly, you also have to install Mali GPU drivers on your hikey960 board!
You can find the instructions online.

After you have everything read:

To generate figure 9 and 10, go to ML-examples/armnn-mnist, modify mnist_caffe.cpp to
make sure it loads different DL models. Then use makefile to compile it as a binary,
copy all of the files including the binaries and the libraries to hikey960, and run
your experiments.

To generate figure 11, you need to checkout the benchmark branch of hikey960-3.5.0,
which tells you how to measure the overhead of SecDeep.

To generate figure 12, modify the key length in hikey960-3.5.0.

To generate figure 13, modify the number of table entries in hikey960-3.5.0.

To generate figure 14, you can use the same data generated from figure 9. I've
added the tracing points there.

To generate figure 15 and 16, use the Monsoon power monitor to repeat the experiment
for figure 9.
