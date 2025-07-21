# Maintainer: Daniel Bermond <dbermond@archlinux.org>

pkgname=ffmpeg-full-git
pkgver=7.2.r120333.gf944a70fcc
pkgrel=1
_svt_hevc_ver='ed80959ebb5586aa7763c91a397d44be1798587c'
pkgdesc='Complete solution to record, convert and stream audio and video (all possible features including libfdk-aac; git version)'
arch=('x86_64')
url='https://www.ffmpeg.org/'
license=('LicenseRef-nonfree-and-unredistributable')
depends=(
    'alsa-lib'
    'aom'
    'aribb24'
    'avisynthplus'
    'bzip2'
    'cairo'
    'celt'
    'codec2'
    'cuda'
    'dav1d'
    'flite1'
    'fontconfig'
    'freetype2'
    'frei0r-plugins'
    'fribidi'
    'gcc-libs'
    'glib2'
    'glibc'
    'glslang'
    'gmp'
    'gnutls'
    'gsm'
    'harfbuzz'
    'jack'
    'kvazaar'
    'ladspa'
    'lame'
    'lcevcdec'
    'lcms2'
    'lensfun-git'
    'libass'
    'libavc1394'
    'libbluray'
    'libbs2b'
    'libcaca'
    'libcdio-paranoia'
    'libdc1394'
    'libdrm'
    'libdvdnav'
    'libdvdread'
    'libfdk-aac'
    'libgcrypt'
    'libgl'
    'libgme'
    'libiec61883'
    'libilbc'
    'libjxl'
    'liblc3'
    'libmodplug'
    'libmysofa'
    'libomxil-bellagio'
    'libopenmpt'
    'libplacebo'
    'libpulse'
    'librabbitmq-c'
    'libraw1394'
    'librist'
    'librsvg'
    'libsoxr'
    'libssh'
    'libtheora'
    'libva'
    'libvdpau'
    'libvorbis'
    'libvpl'
    'libvpx'
    'libx11'
    'libxcb'
    'libxext'
    'libxml2'
    'libxv'
    'libwebp'
    'lilv'
    'lv2'
    'ocl-icd'
    'openal'
    'openapv'
    'opencore-amr'
    'opencv2'
    'openh264'
    'openjpeg2'
    'openvino'
    'opus'
    'qrencode'
    'quirc'
    'rav1e'
    'rtmpdump'
    'rubberband'
    'sdl2'
    'smbclient'
    'snappy'
    'sndio'
    'speex'
    'spirv-tools'
    'srt'
    'svt-av1'
    'svt-hevc'
    'svt-vp9'
    'tesseract'
    'twolame'
    'v4l-utils'
    'vapoursynth'
    'vid.stab'
    'vmaf'
    'vulkan-icd-loader'
    'x264'
    'x265'
    'xvidcore'
    'xz'
    'zeromq'
    'zimg'
    'zlib'
    'zvbi'
    # aur:
    'chromaprint-fftw'
    'davs2'
    'libaribcaption'
    'libklvanc'
    'rockchip-mpp'
    'shine'
    'uavs3d-git'
    'vo-amrwbenc'
    'vvenc'
    'xavs'
    'xavs2'
    'xevd'
    'xeve'
)
optdepends=(
    'nvidia-utils: for NVIDIA NVDEC/NVENC support'
    'vpl-runtime: for Intel Quick Sync Video'
)
makedepends=(
    'git'
    'patchutils'
    'clang'
    'nasm'
    'ffnvcodec-headers'
    'opencl-headers'
    'vulkan-headers'
    # aur:
    'amf-headers-git'
    'decklink-sdk'
)
provides=(
    'ffmpeg'
    'ffmpeg-full'
    'ffmpeg-git'
    'libavcodec.so'
    'libavdevice.so'
    'libavfilter.so'
    'libavformat.so'
    'libavutil.so'
    'libswscale.so'
    'libswresample.so'
)
conflicts=('ffmpeg')
source=('git+https://git.ffmpeg.org/ffmpeg.git'
        '010-ffmpeg-add-svt-hevc.patch'
        "020-ffmpeg-add-svt-hevc-docs-g${_svt_hevc_ver:0:7}.patch"::"https://raw.githubusercontent.com/OpenVisualCloud/SVT-HEVC/${_svt_hevc_ver}/ffmpeg_plugin/0002-doc-Add-libsvt_hevc-encoder-docs.patch"
        '030-ffmpeg-add-svt-vp9.patch'
        '040-ffmpeg-add-av_stream_get_first_dts-for-chromium.patch'
        '050-ffmpeg-fix-segfault-with-avisynthplus.patch'
        '060-ffmpeg-fix-cuda-nvcc-with-gcc14.patch'
        '070-ffmpeg-lcevcdec4.0.0-fix.patch'
        'LICENSE')
sha256sums=('SKIP'
            '96a11444cead07b32a1dac051a88fe0b2f6d14ee6ae95a286a08d2dbf10363f8'
            'a164ebdc4d281352bf7ad1b179aae4aeb33f1191c444bed96cb8ab333c046f81'
            '89192f9b0a63e8e83d024b79ad9fe6bf78f9bf083ca2e9c4db065792726c0234'
            '5cb2475de410f5696072687af88e91461cdacd1bb636ac14a3b348e3383934f1'
            '26419f819d1f3e4d0534995b73d05a8195bc7c892b74c37c3880085af027515b'
            '8acbe1b670479ac4747ae2a78a9d57b8467448dca1d758fb4ec6d08bea6469de'
            '60557f9842ad53a7e20e17f77dcea06cf53337a2bbb8679fd07e50086d582995'
            '04a7176400907fd7db0d69116b99de49e582a6e176b3bfb36a03e50a4cb26a36')

prepare() {
    rm -f ffmpeg/libavcodec/libsvt_{hevc,vp9}.c
    patch -d ffmpeg -Np1 -i "${srcdir}/010-ffmpeg-add-svt-hevc.patch"
    patch -d ffmpeg -Np1 -i "${srcdir}/020-ffmpeg-add-svt-hevc-docs-g${_svt_hevc_ver:0:7}.patch"
    patch -d ffmpeg -Np1 -i "${srcdir}/030-ffmpeg-add-svt-vp9.patch"
    patch -d ffmpeg -Np1 -i "${srcdir}/040-ffmpeg-add-av_stream_get_first_dts-for-chromium.patch"
    patch -d ffmpeg -Np1 -i "${srcdir}/050-ffmpeg-fix-segfault-with-avisynthplus.patch"
    patch -d ffmpeg -Np1 -i "${srcdir}/060-ffmpeg-fix-cuda-nvcc-with-gcc14.patch"
    patch -d ffmpeg -Np1 -i "${srcdir}/070-ffmpeg-lcevcdec4.0.0-fix.patch"
}

pkgver() {
    printf '%s.r%s.g%s' "$(git -C ffmpeg describe --tags --long | awk -F'-' '{ sub(/^n/, "", $1); print $1 }')" \
                        "$(git -C ffmpeg describe --tags --match 'N' | awk -F'-' '{ print $2 }')" \
                        "$(git -C ffmpeg rev-parse --short HEAD)"
}

build() {
    cd ffmpeg
    printf '%s\n' '  -> Running ffmpeg configure script...'
    
    export CFLAGS+=' -isystem/opt/cuda/include'
    export LDFLAGS+=' -L/opt/cuda/lib64'
    
    # fix build of libavfilter/asrc_flite.c with gcc 14
    export CFLAGS+=' -Wno-incompatible-pointer-types'
    
    ./configure \
        --prefix='/usr' \
        --enable-lto \
        \
        --disable-rpath \
        --enable-gpl \
        --enable-version3 \
        --enable-nonfree \
        --enable-shared \
        --disable-static \
        --disable-stripping \
        --disable-htmlpages \
        --enable-gray \
        \
        --enable-alsa \
        --enable-avisynth \
        --enable-bzlib \
        --enable-chromaprint \
        --enable-frei0r \
        --enable-gcrypt \
        --enable-gmp \
        --enable-gnutls \
        --enable-iconv \
        --enable-ladspa \
        --enable-lcms2 \
        --enable-libaom \
        --enable-libaribb24 \
        --enable-libaribcaption \
        --enable-libass \
        --enable-libbluray \
        --enable-libbs2b \
        --enable-libcaca \
        --enable-libcelt \
        --enable-libcdio \
        --enable-libcodec2 \
        --enable-libdav1d \
        --enable-libdavs2 \
        --enable-libdc1394 \
        --enable-libdvdnav \
        --enable-libdvdread \
        --enable-libfdk-aac \
        --enable-libflite \
        --enable-libfontconfig \
        --enable-libfreetype \
        --enable-libfribidi \
        --enable-libharfbuzz \
        --enable-libglslang \
        --enable-libgme \
        --enable-libgsm \
        --enable-libiec61883 \
        --enable-libilbc \
        --enable-libjack \
        --enable-libjxl \
        --enable-libklvanc \
        --enable-libkvazaar \
        --enable-liblc3 \
        --enable-liblcevc-dec \
        --enable-liblensfun \
        --enable-libmodplug \
        --enable-libmp3lame \
        --enable-liboapv \
        --enable-libopencore-amrnb \
        --enable-libopencore-amrwb \
        --enable-libopencv \
        --enable-libopenh264 \
        --enable-libopenjpeg \
        --enable-libopenmpt \
        --enable-libopenvino \
        --enable-libopus \
        --enable-libplacebo \
        --enable-libpulse \
        --enable-libqrencode \
        --enable-libquirc \
        --enable-librabbitmq \
        --enable-librav1e \
        --enable-librist \
        --enable-librsvg \
        --enable-librubberband \
        --enable-librtmp  \
        --disable-libshaderc \
        --enable-libshine \
        --enable-libsmbclient \
        --enable-libsnappy \
        --enable-libsoxr \
        --enable-libspeex \
        --enable-libsrt \
        --enable-libssh \
        --enable-libsvtav1 \
        --enable-libsvthevc \
        --enable-libsvtvp9 \
        --disable-libtensorflow \
        --enable-libtesseract \
        --enable-libtheora \
        --disable-libtls \
        --disable-libtorch \
        --enable-libtwolame \
        --enable-libuavs3d \
        --enable-libv4l2 \
        --enable-libvidstab \
        --enable-libvmaf \
        --enable-libvo-amrwbenc \
        --enable-libvorbis \
        --enable-libvpx \
        --enable-libvvenc \
        --enable-libwebp \
        --enable-libx264 \
        --enable-libx265 \
        --enable-libxevd \
        --enable-libxeve \
        --enable-libxavs \
        --enable-libxavs2 \
        --enable-libxcb \
        --enable-libxcb-shm \
        --enable-libxcb-xfixes \
        --enable-libxcb-shape \
        --enable-libxvid \
        --enable-libxml2 \
        --enable-libzimg \
        --enable-libzmq \
        --enable-libzvbi \
        --enable-lv2 \
        --enable-lzma \
        --enable-decklink \
        --disable-mbedtls \
        --enable-libmysofa \
        --enable-openal \
        --enable-opencl \
        --enable-opengl \
        --disable-openssl \
        --disable-pocketsphinx \
        --enable-sndio \
        --enable-sdl2 \
        --enable-vapoursynth \
        --enable-vulkan \
        --enable-xlib \
        --enable-zlib \
        \
        --enable-amf \
        --enable-cuda-nvcc \
        --enable-cuda-llvm \
        --enable-cuvid \
        --enable-ffnvcodec \
        --enable-libdrm \
        --enable-libvpl \
        --enable-libnpp \
        --enable-nvdec \
        --enable-nvenc \
        --disable-ohcodec \
        --enable-omx \
        --enable-rkmpp \
        --enable-v4l2-m2m \
        --enable-vaapi \
        --enable-vdpau
    make
    make tools/qt-faststart
}

package() {
    make -C ffmpeg DESTDIR="$pkgdir" install
    install -D -m755 ffmpeg/tools/qt-faststart -t "${pkgdir}/usr/bin"
    install -D -m644 LICENSE -t "${pkgdir}/usr/share/licenses/${pkgname}"
}
