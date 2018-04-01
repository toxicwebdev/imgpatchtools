# brotli
Convert system.new.dat.br to system.new.dat


Options:
- -#                          compression level (0-9)
- -c, --stdout                write on standard output
- -d, --decompress            decompress
- -f, --force                 force output file overwrite
- -h, --help                  display this help and exit
- -j, --rm                    remove source file(s)
- -k, --keep                  keep source file(s) (default)
- -n, --no-copy-stat          do not copy source file(s) attributes
- -o FILE, --output=FILE      output file (only if 1 input file)
- -q NUM, --quality=NUM       compression level (0-11)
- -t, --test                  test compressed file integrity
- -v, --verbose               verbose mode
- -w NUM, --lgwin=NUM         set LZ77 window size (0, 10-24) (default:22)
                              window size = 2*NUM - 16
                              0 lets compressor choose the optimal value
- -S SUF, --suffix=SUF        output file suffix (default:'.br')
- -V, --version               display version and exit
- -Z, --best                  use best compression level (11) (default)

Simple options could be coalesced, i.e. '-9kf' is equivalent to '-9 -k -f'.
With no FILE, or when FILE is -, read standard input.
All arguments after '--' are treated as files.

## Info
For more information about this binary, visit https://github.com/google/brotli
