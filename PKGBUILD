# Maintainer: Daniel Bermond <dbermond@archlinux.org>

pkgname=ffmpeg-full-git
pkgver=7.1.r115075.gf8a613d6a8
pkgrel=1
_svt_hevc_ver='ed80959ebb5586aa7763c91a397d44be1798587c'
_svt_vp9_ver='3b9a3fa43da4cc5fe60c7d22afe2be15341392ea'
pkgdesc='Complete solution to record, convert and stream audio and video (all possible features including libfdk-aac; git version)'
arch=('x86_64')
url='https://www.ffmpeg.org/'
license=('LicenseRef-nonfree-and-unredistributable')
depends=(
    'alsa-lib'
    'aom'
    'aribb24'
    'libaribcaption'
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
    'glib2'
    'glslang'
    'gmp'
    'gnutls'
    'gsm'
    'harfbuzz'
    'jack'
    'kvazaar'
    'ladspa'
    'lame'
    'libavc1394'
    'lcms2'
    'lensfun-git'
    'libass'
    'libbluray'
    'libbs2b'
    'libcaca'
    'libcdio-paranoia'
    'libdc1394'
    'libdrm'
    'libfdk-aac'
    'libgcrypt'
    'libgl'
    'libgme'
    'libiec61883'
    'libilbc'
    'libjxl'
    'libmodplug'
    'libmysofa'
    'libomxil-bellagio'
    'libopenmpt'
    'libplacebo'
    'libpulse'
    'librabbitmq-c'
    'libraw1394'
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
    'vpl-runtime'
    'vulkan-icd-loader'
    'x264'
    'x265'
    'xvidcore'
    'xz'
    'zeromq'
    'zimg'
    'zlib'
    'zvbi'
    'chromaprint-fftw'
    'davs2'
    'libklvanc'
    'librist'
    'rockchip-mpp'
    'shine'
    'uavs3d-git'
    'vo-amrwbenc'
    'xavs'
    'xavs2'
    'xevd'
    'xeve'
)
makedepends=('git' 'clang' 'amf-headers' 'ffnvcodec-headers' 'nasm' 'opencl-headers'
             'vulkan-headers' 'decklink-sdk')
provides=('libavcodec.so' 'libavdevice.so' 'libavfilter.so' 'libavformat.so'
          'libavutil.so' 'libpostproc.so' 'libswscale.so' 'libswresample.so'
          'ffmpeg' 'ffmpeg-full' 'ffmpeg-git')
conflicts=('ffmpeg')
source=('git+https://git.ffmpeg.org/ffmpeg.git'
        #"005-ffmpeg-add-svt-hevc-g${_svt_hevc_ver:0:7}.patch"
        #"006-ffmpeg-add-svt-vp9-g${_svt_vp9_ver:0:7}.patch"
        "010-ffmpeg-add-svt-hevc-g${_svt_hevc_ver:0:7}.patch"::"https://raw.githubusercontent.com/OpenVisualCloud/SVT-HEVC/${_svt_hevc_ver}/ffmpeg_plugin/master-0001-lavc-svt_hevc-add-libsvt-hevc-encoder-wrapper.patch"
        "020-ffmpeg-add-svt-hevc-docs-g${_svt_hevc_ver:0:7}.patch"::"https://raw.githubusercontent.com/OpenVisualCloud/SVT-HEVC/${_svt_hevc_ver}/ffmpeg_plugin/0002-doc-Add-libsvt_hevc-encoder-docs.patch"
        "030-ffmpeg-add-svt-vp9-g${_svt_vp9_ver:0:7}.patch"::"https://raw.githubusercontent.com/OpenVisualCloud/SVT-VP9/${_svt_vp9_ver}/ffmpeg_plugin/master-0001-Add-ability-for-ffmpeg-to-run-svt-vp9.patch"
        '040-ffmpeg-add-av_stream_get_first_dts-for-chromium.patch'
        '050-ffmpeg-fix-segfault-with-avisynthplus.patch'
        '060-ffmpeg-fix-nvidia-vulkan-decoding-segfault.patch'
        'LICENSE')
sha256sums=('SKIP'
            '9047e18d34716812d4ea7eafc1d0fd8b376d922a4b6b4dc20237662fcaf0c996'
            'a164ebdc4d281352bf7ad1b179aae4aeb33f1191c444bed96cb8ab333c046f81'
            '59da61f2b2c556fbe0cdbf84bcc00977ee3d2447085decb21f6298226559f2aa'
            'b54b47f4f3837ddc41227bd2202ea3c62e2ddb06c6cfbd7a9adc304d641d79ba'
            '0e277c0d5e33612ca7a11025958133b17bfbe23168b0aee5bd07f674f6fd7440'
            'f2f73793a45c9dffb033f23c1b10a612abe6528cbd06c04b06e8189d1ef208be'
            '04a7176400907fd7db0d69116b99de49e582a6e176b3bfb36a03e50a4cb26a36')

prepare() {
    rm -f ffmpeg/libavcodec/libsvt_{hevc,vp9}.c
    #cp --remove-destination "$(readlink "010-ffmpeg-add-svt-hevc-g${_svt_hevc_ver:0:7}.patch")" \
    #    "010-ffmpeg-add-svt-hevc-g${_svt_hevc_ver:0:7}.patch"
    #patch -Np1 -i "005-ffmpeg-add-svt-hevc-g${_svt_hevc_ver:0:7}.patch"
    #cp --remove-destination "$(readlink "030-ffmpeg-add-svt-vp9-g${_svt_vp9_ver:0:7}.patch")" \
    #    "030-ffmpeg-add-svt-vp9-g${_svt_vp9_ver:0:7}.patch"
    #patch -Np1 -i "006-ffmpeg-add-svt-vp9-g${_svt_vp9_ver:0:7}.patch"
    patch -d ffmpeg -Np1 -i "${srcdir}/010-ffmpeg-add-svt-hevc-g${_svt_hevc_ver:0:7}.patch"
    patch -d ffmpeg -Np1 -i "${srcdir}/020-ffmpeg-add-svt-hevc-docs-g${_svt_hevc_ver:0:7}.patch"
    patch -d ffmpeg -Np1 -i "${srcdir}/030-ffmpeg-add-svt-vp9-g${_svt_vp9_ver:0:7}.patch"
    patch -d ffmpeg -Np1 -i "${srcdir}/040-ffmpeg-add-av_stream_get_first_dts-for-chromium.patch"
    patch -d ffmpeg -Np1 -i "${srcdir}/050-ffmpeg-fix-segfault-with-avisynthplus.patch"
    patch -d ffmpeg -Np1 -i "${srcdir}/060-ffmpeg-fix-nvidia-vulkan-decoding-segfault.patch"
}

pkgver() {
    printf '%s.r%s.g%s' "$(git -C ffmpeg describe --tags --long | awk -F'-' '{ sub(/^n/, "", $1); print $1 }')" \
                        "$(git -C ffmpeg describe --tags --match 'N' | awk -F'-' '{ print $2 }')" \
                        "$(git -C ffmpeg rev-parse --short HEAD)"
}

build() {
    cd ffmpeg
    printf '%s\n' '  -> Running ffmpeg configure script...'
    
    export CFLAGS+=' -I/opt/cuda/include'
    export LDFLAGS+=' -L/opt/cuda/lib64'
    export PKG_CONFIG_PATH="/opt/intel/openvino/runtime/lib/intel64/pkgconfig${PKG_CONFIG_PATH:+":${PKG_CONFIG_PATH}"}"
    
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
        --enable-liblensfun \
        --enable-libmodplug \
        --enable-libmp3lame \
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
