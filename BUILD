# --- CPU Target ---
cc_binary(
    name = "mandelbrot_cpu",
    srcs = ["mandelbrot_cpu.cpp"],
    copts = [
        "-std=c++17",
        "-O3",
        "-ffast-math",
        "-march=native",
    ],
)

# --- GPU Target ---
genrule(
    name = "mandelbrot_gpu_obj",
    srcs = ["mandelbrot_gpu.cu"],
    outs = ["mandelbrot_gpu.o"],
    cmd = "nvcc -I/usr/local/cuda/include -std=c++17 -O3 --use_fast_math -c $< -o $@",
)

cc_binary(
    name = "mandelbrot_gpu",
    srcs = [":mandelbrot_gpu_obj"],
    linkopts = [
        "-L/usr/local/cuda/lib64",
        "-lcudart",
    ],
)
