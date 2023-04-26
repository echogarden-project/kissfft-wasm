PROJ=kissfft

EMCCFLAGS=-s WASM=1 -s ALLOW_MEMORY_GROWTH=1 -s EXPORTED_FUNCTIONS="['_malloc', '_free', '_kiss_fft_alloc', '_kiss_fft', '_kiss_fft_stride', '_kiss_fft_cleanup', '_kiss_fft_next_fast_size', '_kiss_fftr_alloc', '_kiss_fftr', '_kiss_fftri']" -s EXPORTED_RUNTIME_METHODS="['getValue', 'setValue', 'cwrap']" -s MODULARIZE=1 -s EXPORT_NAME="KissFFT"

all: src/kiss_fft.c src/kiss_fftr.c
	emcc $(EMCCFLAGS) -O3 -o $(PROJ).cjs -I src $^

.PHONY: clean
clean:
	rm -f $(PROJ).cjs $(PROJ).wasm
