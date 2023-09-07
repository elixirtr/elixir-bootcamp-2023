# asdf

Elixir ve Erlang kurulumunu asdf(version manager) ile yapacağız. Bazı sürümlerde özellikle son sürümlerde dialyzer ve analyzer ayrıca language server hatalı çalışabilmekte.
Bu hataların önüne geçebilmek ve herkeste aynı sürümün olmasını sağlamak için kurulumların asdf ile yapılması gerekmektedir.

Asdf kurulumu için installation guide takip edilebilir. Zaten tüm os ve profile'ler için açıkça ve temiz bir rehberi mevcut.

[asdf installation guide](https://asdf-vm.com/guide/getting-started.html)

## Erlang Install with asdf

### Before asdf install

#### Ubuntu 20.04 LTS

```
apt-get -y install build-essential autoconf m4 libncurses5-dev libwxgtk3.0-gtk3-dev
libwxgtk-webview3.0-gtk3-dev libgl1-mesa-dev libglu1-mesa-dev libpng-dev libssh-dev unixodbc-dev
xsltproc fop libxml2-utils libncurses-dev openjdk-11-jdk
```

#### Arch

```
pacman -S --needed base-devel
pacman -S libssh
sudo pacman -S unixodbc
pacman -S glu mesa wxwidgets-gtk3 libpng
```

#### Mac

```
brew install autoconf
brew install openssl
brew install wxwidgets
```

### Install
```
asdf plugin add erlang https://github.com/asdf-vm/asdf-erlang.git
export KERL_CONFIGURE_OPTIONS="--disable-debug --without-javac"
asdf install erlang 25.3.2.6
asdf global erlang 25.3.2.6

erl -v

## Output
Erlang/OTP 25 [erts-13.2.2.3] [source] [64-bit] [smp:8:8] [ds:8:8:10] [async-threads:1] [jit]

Eshell V13.2.2.3  (abort with ^G)
```

## Elixir Install with asdf

Debian tabanlı bir dağıtım kullanıyorsanız unzip yüklemelisiniz.

```sudo apt-get install unzip```

```
asdf plugin-add elixir https://github.com/asdf-vm/asdf-elixir.git

asdf install elixir 1.14.5-otp-25
asdf global elixir 1.14.5-otp-25

elixir -v

## Output

Erlang/OTP 25 [erts-13.2.2.3] [source] [64-bit] [smp:8:8] [ds:8:8:10] [async-threads:1] [jit]

Elixir 1.14.5 (compiled with Erlang/OTP 25)
```

Sorun yaşamanız halinde faydalı linkler
[asdf erlang  plugin](https://github.com/asdf-vm/asdf-erlang)
[asdf elixir  plugin](https://github.com/asdf-vm/asdf-elixir/tree/master)
