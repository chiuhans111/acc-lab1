Starter code for 6.S894 [Lab 1](https://accelerated-computing-class.github.io/fall24/labs/lab1).

Run code: (hacky way)

```sh
# CPU
bazel run --run_under="cd $PWD &&" //:mandelbrot_cpu
# GPU
bazel run --run_under="cd $PWD &&" //:mandelbrot_gpu
```