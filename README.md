文件来源于https://github.com/erfanoabdi
https://github.com/xpirt
### 条件

需要python>=2.7
ubuntu

## imgpatchtools用法

```
./BlockImageUpdate <system.img> <system.transfer.list> <system.new.dat> <system.patch.dat>
```
参数:
- `<system.img>` = block device (or file) to modify in-place
- `<system.transfer.list>` = transfer list (blob) from OTA/rom zip
- `<system.new.dat>` = new data stream from OTA/rom zip
- `<system.patch.dat>` = patch stream from OTA/rom zip

```
./ApplyPatchfn <file> <target> <tgt_sha1> <size> <init_sha1(1)> <patch(1)> [init_sha1(2)] [patch(2)]...
```
参数:
- `<file>` = source file from rom zip
- `<target>` = target file (use "-" to patch source file)
- `<tgt_sha1>` = target SHA1 Sum after patching
- `<size>` = file size
- `<init_sha1>` = file SHA1 sum
- `<patch>` = patch file (.p) from OTA zip

# 其他

## 将system.new.dat, system.patch.dat, system.transfer.listt转换成system.img


### 用法

```
sdat2img.py <transfer_list> <system_new_file> [system_img]
```
参数:
- `<transfer_list>` = input, system.transfer.list from rom zip
- `<system_new_file>` = input, system.new.dat from rom zip
- `[system_img]` = output ext4 raw image file (optional)

## 将system.img转换成system.new.dat, system.patch.dat, system.transfer.list

### 安装img2simg

```
sudo apt install android-tools-fsutils
```

### 利用img2simg将system.img从raw ext4 image转换成为sparse image

```
img2simg <raw_image_file> <sparse_image_file> [<block_size>]
```

### 利用img2sdat将system.img(sparse image)转换成system.new.dat, system.patch.dat, system.transfer.list

```
img2sdat.py <system_img> [outdir] [version]
```
参数
- `<system_img>` = input system image
- `[outdir]` = output directory (current directory by default)
- `[version]` = transfer list version number (1 - 5.0, 2 - 5.1, 3 - 6.0, 4 - 7.0, will be asked by default, more info on xda thread)
