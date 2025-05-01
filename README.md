# MacMiniSetup
Notes on getting Mac Mini M4 setup.  Includes AI tools.

For starters, I followed [pytorch-apple-silicon](https://github.com/mrdbourke/pytorch-apple-silicon) by [mrdbourke](https://github.com/mrdbourke).  I want to get the basic Pytorch / Python working ontop of Apple Silicon.

# Setup Miniforge3
Miniforge installs conda, the tool for locally creating Python environments. I just learned about this.  conda is sort of like [venv](https://docs.python.org/3/library/venv.html). Conda is used to create environments with different python versions. The miniforge environment is installed in the user home directory.

## Download
```
jkozikÉJacks-Mac-mini Downloads % curl -OL https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-arm64.sh
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
100 60.3M  100 60.3M    0     0  12.5M      0  0:00:04  0:00:04 --:--:-- 13.4M
jkozikÉJacks-Mac-mini Downloads % ls  -lasth
total 125056
125056 -rw-r--r--É  1 jkozik  staff    60M May  1 18:31 Miniforge3-MacOSX-arm64.sh
     0 drwx------+  4 jkozik  staff   128B May  1 18:26 .
     0 drwxr-x---+ 20 jkozik  staff   640B May  1 18:21 ..
     0 -rw-r--r--   1 jkozik  staff     0B Apr 24 11:55 .localized
jkozikÉJacks-Mac-mini Downloads %
```
## Install
```
jkozikÉJacks-Mac-mini Downloads % chmod +x ü/Downloads/Miniforge3-MacOSX-arm64.sh
sh ü/Downloads/Miniforge3-MacOSX-arm64.sh
source ü/miniforge3/bin/activate
jkozikÉJacks-Mac-mini Downloads % chmod +x ü/Downloads/Miniforge3-MacOSX-arm64.sh
jkozikÉJacks-Mac-mini Downloads % sh ü/Downloads/Miniforge3-MacOSX-arm64.sh

Welcome to Miniforge3 25.3.0-1

In order to continue the installation process, please review the license
agreement.
Please, press ENTER to continue
>>>
Miniforge installer code uses BSD-3-Clause license as stated below.

Binary packages that come with it have their own licensing terms
and by installing miniforge you agree to the licensing terms of individual
packages as well. They include different OSI-approved licenses including
the GNU General Public License and can be found in pkgs/<pkg-name>/info/licenses
folders.

Miniforge installer comes with a bootstrapping executable that is used
when installing miniforge and is deleted after miniforge is installed.
The bootstrapping executable uses micromamba, cli11, cpp-filesystem,
curl, c-ares, krb5, libarchive, libev, lz4, nghttp2, openssl, libsolv,
nlohmann-json, reproc and zstd which are licensed under BSD-3-Clause,
MIT and OpenSSL licenses. Licenses and copyright notices of these
projects can be found at the following URL.
https://github.com/conda-forge/micromamba-feedstock/tree/master/recipe.

=============================================================================

Copyright (c) 2019-2022, conda-forge
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this
list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice,
this list of conditions and the following disclaimer in the documentation
and/or other materials provided with the distribution.

3. Neither the name of the copyright holder nor the names of its contributors
may be used to endorse or promote products derived from this software without
specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND
ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.


Do you accept the license terms? ÄyesönoÅ
>>> yes

Miniforge3 will now be installed into this location:
/Users/jkozik/miniforge3

  - Press ENTER to confirm the location
  - Press CTRL-C to abort the installation
  - Or specify a different location below

Ä/Users/jkozik/miniforge3Å >>>
PREFIX=/Users/jkozik/miniforge3
Unpacking payload ...
Extracting bzip2-1.0.8-h99b78c6_7.conda
Extracting c-ares-1.34.4-h5505292_0.conda
Extracting ca-certificates-2025.1.31-hf0a4a13_0.conda
Extracting icu-75.1-hfee45f7_0.conda
Extracting libcxx-20.1.2-ha82da77_0.conda
Extracting libev-4.33-h93a5062_2.conda
Extracting libexpat-2.7.0-h286801f_0.conda
Extracting libffi-3.4.6-h1da3d7d_1.conda
Extracting libiconv-1.18-hfe07756_1.conda
Extracting liblzma-5.8.1-h39f12f2_0.conda
Extracting libzlib-1.3.1-h8359307_2.conda
Extracting lzo-2.10-h93a5062_1001.conda
Extracting ncurses-6.5-h5e97a16_3.conda
Extracting pybind11-abi-4-hd8ed1ab_3.tar.bz2
Extracting python_abi-3.12-6_cp312.conda
Extracting reproc-14.2.5.post0-h5505292_0.conda
Extracting tzdata-2025b-h78e105d_0.conda
Extracting cpp-expected-1.1.0-hffc8910_0.conda
Extracting fmt-11.1.4-h440487c_1.conda
Extracting libedit-3.1.20250104-pl5321hafb1f1b_0.conda
Extracting libsolv-0.7.30-h6c9b7f8_0.conda
Extracting libsqlite-3.49.1-h3f77e49_2.conda
Extracting libxml2-2.13.7-h52572c6_1.conda
Extracting lz4-c-1.10.0-h286801f_1.conda
Extracting nlohmann_json-3.11.3-h00cdb27_1.conda
Extracting openssl-3.4.1-h81ee809_0.conda
Extracting readline-8.2-h1d1bf99_2.conda
Extracting reproc-cpp-14.2.5.post0-h286801f_0.conda
Extracting simdjson-3.12.3-ha393de7_0.conda
Extracting tk-8.6.13-h5083fa2_1.conda
Extracting yaml-cpp-0.8.0-h13dd4ca_0.conda
Extracting zstd-1.5.7-h6491c7d_2.conda
Extracting krb5-1.21.3-h237132a_0.conda
Extracting libarchive-3.7.7-h3b16cec_3.conda
Extracting libnghttp2-1.64.0-h6d7220d_0.conda
Extracting libssh2-1.11.1-h9cc3647_0.conda
Extracting python-3.12.9-hc22306f_1_cpython.conda
Extracting spdlog-1.15.2-h008cadb_0.conda
Extracting libcurl-8.13.0-h73640d1_0.conda
Extracting menuinst-2.2.0-py312h81bd7bf_0.conda
Extracting archspec-0.2.5-pyhd8ed1ab_0.conda
Extracting boltons-24.0.0-pyhd8ed1ab_1.conda
Extracting brotli-python-1.1.0-py312hde4cb15_2.conda
Extracting certifi-2025.1.31-pyhd8ed1ab_0.conda
Extracting charset-normalizer-3.4.1-pyhd8ed1ab_0.conda
Extracting colorama-0.4.6-pyhd8ed1ab_1.conda
Extracting distro-1.9.0-pyhd8ed1ab_1.conda
Extracting frozendict-2.4.6-py312h0bf5046_0.conda
Extracting hpack-4.1.0-pyhd8ed1ab_0.conda
Extracting hyperframe-6.1.0-pyhd8ed1ab_0.conda
Extracting idna-3.10-pyhd8ed1ab_1.conda
Extracting jsonpointer-3.0.0-py312h81bd7bf_1.conda
Extracting libmamba-2.0.8-h7c3736b_2.conda
Extracting packaging-24.2-pyhd8ed1ab_2.conda
Extracting platformdirs-4.3.7-pyh29332c3_0.conda
Extracting pluggy-1.5.0-pyhd8ed1ab_1.conda
Extracting pycosat-0.6.6-py312hea69d52_2.conda
Extracting pycparser-2.22-pyh29332c3_1.conda
Extracting pysocks-1.7.1-pyha55dd90_7.conda
Extracting ruamel.yaml.clib-0.2.8-py312h0bf5046_1.conda
Extracting setuptools-78.1.0-pyhff2d567_0.conda
Extracting truststore-0.10.1-pyh29332c3_0.conda
Extracting wheel-0.45.1-pyhd8ed1ab_1.conda
Extracting cffi-1.17.1-py312h0fad829_0.conda
Extracting h2-4.2.0-pyhd8ed1ab_0.conda
Extracting jsonpatch-1.33-pyhd8ed1ab_1.conda
Extracting libmambapy-2.0.8-py312h9b24f82_2.conda
Extracting mamba-2.0.8-h105ca85_2.conda
Extracting pip-25.0.1-pyh8b19718_0.conda
Extracting ruamel.yaml-0.18.10-py312hea69d52_0.conda
Extracting tqdm-4.67.1-pyhd8ed1ab_1.conda
Extracting zstandard-0.23.0-py312hea69d52_1.conda
Extracting conda-package-streaming-0.11.0-pyhd8ed1ab_1.conda
Extracting urllib3-2.3.0-pyhd8ed1ab_0.conda
Extracting requests-2.32.3-pyhd8ed1ab_1.conda
Extracting conda-package-handling-2.4.0-pyh7900ff3_2.conda
Extracting conda-libmamba-solver-25.3.0-pyhd8ed1ab_0.conda
Extracting conda-25.3.0-py312h81bd7bf_0.conda

Installing base environment...

Transaction

  Prefix: /Users/jkozik/miniforge3

  Updating specs:

   - bzip2==1.0.8=h99b78c6_7
   - c-ares==1.34.4=h5505292_0
   - ca-certificates==2025.1.31=hf0a4a13_0
   - icu==75.1=hfee45f7_0
   - libcxx==20.1.2=ha82da77_0
   - libev==4.33=h93a5062_2
   - libexpat==2.7.0=h286801f_0
   - libffi==3.4.6=h1da3d7d_1
   - libiconv==1.18=hfe07756_1
   - liblzma==5.8.1=h39f12f2_0
   - libzlib==1.3.1=h8359307_2
   - lzo==2.10=h93a5062_1001
   - ncurses==6.5=h5e97a16_3
   - pybind11-abi==4=hd8ed1ab_3
   - python_abi==3.12=6_cp312
   - reproc==14.2.5.0post0=h5505292_0
   - tzdata==2025b=h78e105d_0
   - cpp-expected==1.1.0=hffc8910_0
   - fmt==11.1.4=h440487c_1
   - libedit==3.1.20250104=pl5321hafb1f1b_0
   - libsolv==0.7.30=h6c9b7f8_0
   - libsqlite==3.49.1=h3f77e49_2
   - libxml2==2.13.7=h52572c6_1
   - lz4-c==1.10.0=h286801f_1
   - nlohmann_json==3.11.3=h00cdb27_1
   - openssl==3.4.1=h81ee809_0
   - readline==8.2=h1d1bf99_2
   - reproc-cpp==14.2.5.0post0=h286801f_0
   - simdjson==3.12.3=ha393de7_0
   - tk==8.6.13=h5083fa2_1
   - yaml-cpp==0.8.0=h13dd4ca_0
   - zstd==1.5.7=h6491c7d_2
   - krb5==1.21.3=h237132a_0
   - libarchive==3.7.7=h3b16cec_3
   - libnghttp2==1.64.0=h6d7220d_0
   - libssh2==1.11.1=h9cc3647_0
   - python==3.12.9=hc22306f_1_cpython
   - spdlog==1.15.2=h008cadb_0
   - libcurl==8.13.0=h73640d1_0
   - menuinst==2.2.0=py312h81bd7bf_0
   - archspec==0.2.5=pyhd8ed1ab_0
   - boltons==24.0.0=pyhd8ed1ab_1
   - brotli-python==1.1.0=py312hde4cb15_2
   - certifi==2025.1.31=pyhd8ed1ab_0
   - charset-normalizer==3.4.1=pyhd8ed1ab_0
   - colorama==0.4.6=pyhd8ed1ab_1
   - distro==1.9.0=pyhd8ed1ab_1
   - frozendict==2.4.6=py312h0bf5046_0
   - hpack==4.1.0=pyhd8ed1ab_0
   - hyperframe==6.1.0=pyhd8ed1ab_0
   - idna==3.10=pyhd8ed1ab_1
   - jsonpointer==3.0.0=py312h81bd7bf_1
   - libmamba==2.0.8=h7c3736b_2
   - packaging==24.2=pyhd8ed1ab_2
   - platformdirs==4.3.7=pyh29332c3_0
   - pluggy==1.5.0=pyhd8ed1ab_1
   - pycosat==0.6.6=py312hea69d52_2
   - pycparser==2.22=pyh29332c3_1
   - pysocks==1.7.1=pyha55dd90_7
   - ruamel.yaml.clib==0.2.8=py312h0bf5046_1
   - setuptools==78.1.0=pyhff2d567_0
   - truststore==0.10.1=pyh29332c3_0
   - wheel==0.45.1=pyhd8ed1ab_1
   - cffi==1.17.1=py312h0fad829_0
   - h2==4.2.0=pyhd8ed1ab_0
   - jsonpatch==1.33=pyhd8ed1ab_1
   - libmambapy==2.0.8=py312h9b24f82_2
   - mamba==2.0.8=h105ca85_2
   - pip==25.0.1=pyh8b19718_0
   - ruamel.yaml==0.18.10=py312hea69d52_0
   - tqdm==4.67.1=pyhd8ed1ab_1
   - zstandard==0.23.0=py312hea69d52_1
   - conda-package-streaming==0.11.0=pyhd8ed1ab_1
   - urllib3==2.3.0=pyhd8ed1ab_0
   - requests==2.32.3=pyhd8ed1ab_1
   - conda-package-handling==2.4.0=pyh7900ff3_2
   - conda-libmamba-solver==25.3.0=pyhd8ed1ab_0
   - conda==25.3.0=py312h81bd7bf_0


  Package                         Version  Build               Channel         Size
─────────────────────────────────────────────────────────────────────────────────────
  Install:
─────────────────────────────────────────────────────────────────────────────────────

  + archspec                        0.2.5  pyhd8ed1ab_0        conda-forge
  + boltons                        24.0.0  pyhd8ed1ab_1        conda-forge
  + brotli-python                   1.1.0  py312hde4cb15_2     conda-forge
  + bzip2                           1.0.8  h99b78c6_7          conda-forge
  + c-ares                         1.34.4  h5505292_0          conda-forge
  + ca-certificates             2025.1.31  hf0a4a13_0          conda-forge
  + certifi                     2025.1.31  pyhd8ed1ab_0        conda-forge
  + cffi                           1.17.1  py312h0fad829_0     conda-forge
  + charset-normalizer              3.4.1  pyhd8ed1ab_0        conda-forge
  + colorama                        0.4.6  pyhd8ed1ab_1        conda-forge
  + conda                          25.3.0  py312h81bd7bf_0     conda-forge
  + conda-libmamba-solver          25.3.0  pyhd8ed1ab_0        conda-forge
  + conda-package-handling          2.4.0  pyh7900ff3_2        conda-forge
  + conda-package-streaming        0.11.0  pyhd8ed1ab_1        conda-forge
  + cpp-expected                    1.1.0  hffc8910_0          conda-forge
  + distro                          1.9.0  pyhd8ed1ab_1        conda-forge
  + fmt                            11.1.4  h440487c_1          conda-forge
  + frozendict                      2.4.6  py312h0bf5046_0     conda-forge
  + h2                              4.2.0  pyhd8ed1ab_0        conda-forge
  + hpack                           4.1.0  pyhd8ed1ab_0        conda-forge
  + hyperframe                      6.1.0  pyhd8ed1ab_0        conda-forge
  + icu                              75.1  hfee45f7_0          conda-forge
  + idna                             3.10  pyhd8ed1ab_1        conda-forge
  + jsonpatch                        1.33  pyhd8ed1ab_1        conda-forge
  + jsonpointer                     3.0.0  py312h81bd7bf_1     conda-forge
  + krb5                           1.21.3  h237132a_0          conda-forge
  + libarchive                      3.7.7  h3b16cec_3          conda-forge
  + libcurl                        8.13.0  h73640d1_0          conda-forge
  + libcxx                         20.1.2  ha82da77_0          conda-forge
  + libedit                  3.1.20250104  pl5321hafb1f1b_0    conda-forge
  + libev                            4.33  h93a5062_2          conda-forge
  + libexpat                        2.7.0  h286801f_0          conda-forge
  + libffi                          3.4.6  h1da3d7d_1          conda-forge
  + libiconv                         1.18  hfe07756_1          conda-forge
  + liblzma                         5.8.1  h39f12f2_0          conda-forge
  + libmamba                        2.0.8  h7c3736b_2          conda-forge
  + libmambapy                      2.0.8  py312h9b24f82_2     conda-forge
  + libnghttp2                     1.64.0  h6d7220d_0          conda-forge
  + libsolv                        0.7.30  h6c9b7f8_0          conda-forge
  + libsqlite                      3.49.1  h3f77e49_2          conda-forge
  + libssh2                        1.11.1  h9cc3647_0          conda-forge
  + libxml2                        2.13.7  h52572c6_1          conda-forge
  + libzlib                         1.3.1  h8359307_2          conda-forge
  + lz4-c                          1.10.0  h286801f_1          conda-forge
  + lzo                              2.10  h93a5062_1001       conda-forge
  + mamba                           2.0.8  h105ca85_2          conda-forge
  + menuinst                        2.2.0  py312h81bd7bf_0     conda-forge
  + ncurses                           6.5  h5e97a16_3          conda-forge
  + nlohmann_json                  3.11.3  h00cdb27_1          conda-forge
  + openssl                         3.4.1  h81ee809_0          conda-forge
  + packaging                        24.2  pyhd8ed1ab_2        conda-forge
  + pip                            25.0.1  pyh8b19718_0        conda-forge
  + platformdirs                    4.3.7  pyh29332c3_0        conda-forge
  + pluggy                          1.5.0  pyhd8ed1ab_1        conda-forge
  + pybind11-abi                        4  hd8ed1ab_3          conda-forge
  + pycosat                         0.6.6  py312hea69d52_2     conda-forge
  + pycparser                        2.22  pyh29332c3_1        conda-forge
  + pysocks                         1.7.1  pyha55dd90_7        conda-forge
  + python                         3.12.9  hc22306f_1_cpython  conda-forge
  + python_abi                       3.12  6_cp312             conda-forge
  + readline                          8.2  h1d1bf99_2          conda-forge
  + reproc                   14.2.5.post0  h5505292_0          conda-forge
  + reproc-cpp               14.2.5.post0  h286801f_0          conda-forge
  + requests                       2.32.3  pyhd8ed1ab_1        conda-forge
  + ruamel.yaml                   0.18.10  py312hea69d52_0     conda-forge
  + ruamel.yaml.clib                0.2.8  py312h0bf5046_1     conda-forge
  + setuptools                     78.1.0  pyhff2d567_0        conda-forge
  + simdjson                       3.12.3  ha393de7_0          conda-forge
  + spdlog                         1.15.2  h008cadb_0          conda-forge
  + tk                             8.6.13  h5083fa2_1          conda-forge
  + tqdm                           4.67.1  pyhd8ed1ab_1        conda-forge
  + truststore                     0.10.1  pyh29332c3_0        conda-forge
  + tzdata                          2025b  h78e105d_0          conda-forge
  + urllib3                         2.3.0  pyhd8ed1ab_0        conda-forge
  + wheel                          0.45.1  pyhd8ed1ab_1        conda-forge
  + yaml-cpp                        0.8.0  h13dd4ca_0          conda-forge
  + zstandard                      0.23.0  py312hea69d52_1     conda-forge
  + zstd                            1.5.7  h6491c7d_2          conda-forge

  Summary:

  Install: 78 packages

  Total download: 0 B

─────────────────────────────────────────────────────────────────────────────────────



Transaction starting
Linking bzip2-1.0.8-h99b78c6_7
Linking c-ares-1.34.4-h5505292_0
Linking ca-certificates-2025.1.31-hf0a4a13_0
Linking icu-75.1-hfee45f7_0
Linking libcxx-20.1.2-ha82da77_0
Linking libev-4.33-h93a5062_2
Linking libexpat-2.7.0-h286801f_0
Linking libffi-3.4.6-h1da3d7d_1
Linking libiconv-1.18-hfe07756_1
Linking liblzma-5.8.1-h39f12f2_0
Linking libzlib-1.3.1-h8359307_2
Linking lzo-2.10-h93a5062_1001
Linking ncurses-6.5-h5e97a16_3
Linking pybind11-abi-4-hd8ed1ab_3
Linking python_abi-3.12-6_cp312
Linking reproc-14.2.5.post0-h5505292_0
Linking tzdata-2025b-h78e105d_0
Linking cpp-expected-1.1.0-hffc8910_0
Linking fmt-11.1.4-h440487c_1
Linking libedit-3.1.20250104-pl5321hafb1f1b_0
Linking libsolv-0.7.30-h6c9b7f8_0
Linking libsqlite-3.49.1-h3f77e49_2
Linking libxml2-2.13.7-h52572c6_1
Linking lz4-c-1.10.0-h286801f_1
Linking nlohmann_json-3.11.3-h00cdb27_1
Linking openssl-3.4.1-h81ee809_0
Linking readline-8.2-h1d1bf99_2
Linking reproc-cpp-14.2.5.post0-h286801f_0
Linking simdjson-3.12.3-ha393de7_0
Linking tk-8.6.13-h5083fa2_1
Linking yaml-cpp-0.8.0-h13dd4ca_0
Linking zstd-1.5.7-h6491c7d_2
Linking krb5-1.21.3-h237132a_0
Linking libarchive-3.7.7-h3b16cec_3
Linking libnghttp2-1.64.0-h6d7220d_0
Linking libssh2-1.11.1-h9cc3647_0
Linking python-3.12.9-hc22306f_1_cpython
Linking spdlog-1.15.2-h008cadb_0
Linking libcurl-8.13.0-h73640d1_0
Linking menuinst-2.2.0-py312h81bd7bf_0
Linking archspec-0.2.5-pyhd8ed1ab_0
Linking boltons-24.0.0-pyhd8ed1ab_1
Linking brotli-python-1.1.0-py312hde4cb15_2
Linking certifi-2025.1.31-pyhd8ed1ab_0
Linking charset-normalizer-3.4.1-pyhd8ed1ab_0
Linking colorama-0.4.6-pyhd8ed1ab_1
Linking distro-1.9.0-pyhd8ed1ab_1
Linking frozendict-2.4.6-py312h0bf5046_0
Linking hpack-4.1.0-pyhd8ed1ab_0
Linking hyperframe-6.1.0-pyhd8ed1ab_0
Linking idna-3.10-pyhd8ed1ab_1
Linking jsonpointer-3.0.0-py312h81bd7bf_1
Linking libmamba-2.0.8-h7c3736b_2
Linking packaging-24.2-pyhd8ed1ab_2
Linking platformdirs-4.3.7-pyh29332c3_0
Linking pluggy-1.5.0-pyhd8ed1ab_1
Linking pycosat-0.6.6-py312hea69d52_2
Linking pycparser-2.22-pyh29332c3_1
Linking pysocks-1.7.1-pyha55dd90_7
Linking ruamel.yaml.clib-0.2.8-py312h0bf5046_1
Linking setuptools-78.1.0-pyhff2d567_0
Linking truststore-0.10.1-pyh29332c3_0
Linking wheel-0.45.1-pyhd8ed1ab_1
Linking cffi-1.17.1-py312h0fad829_0
Linking h2-4.2.0-pyhd8ed1ab_0
Linking jsonpatch-1.33-pyhd8ed1ab_1
Linking libmambapy-2.0.8-py312h9b24f82_2
Linking mamba-2.0.8-h105ca85_2
Linking pip-25.0.1-pyh8b19718_0
Linking ruamel.yaml-0.18.10-py312hea69d52_0
Linking tqdm-4.67.1-pyhd8ed1ab_1
Linking zstandard-0.23.0-py312hea69d52_1
Linking conda-package-streaming-0.11.0-pyhd8ed1ab_1
Linking urllib3-2.3.0-pyhd8ed1ab_0
Linking requests-2.32.3-pyhd8ed1ab_1
Linking conda-package-handling-2.4.0-pyh7900ff3_2
Linking conda-libmamba-solver-25.3.0-pyhd8ed1ab_0
Linking conda-25.3.0-py312h81bd7bf_0

Transaction finished

installation finished.
Do you wish to update your shell profile to automatically initialize conda?
This will activate conda on startup and change the command prompt when activated.
If you'd prefer that conda's base environment not be activated on startup,
   run the following command when conda is activated:

conda config --set auto_activate_base false

You can undo this by running éconda init --reverse $SHELLé? ÄyesönoÅ
ÄnoÅ >>> yes
no change     /Users/jkozik/miniforge3/condabin/conda
no change     /Users/jkozik/miniforge3/bin/conda
no change     /Users/jkozik/miniforge3/bin/conda-env
no change     /Users/jkozik/miniforge3/bin/activate
no change     /Users/jkozik/miniforge3/bin/deactivate
no change     /Users/jkozik/miniforge3/etc/profile.d/conda.sh
no change     /Users/jkozik/miniforge3/etc/fish/conf.d/conda.fish
no change     /Users/jkozik/miniforge3/shell/condabin/Conda.psm1
no change     /Users/jkozik/miniforge3/shell/condabin/conda-hook.ps1
no change     /Users/jkozik/miniforge3/lib/python3.12/site-packages/xontrib/conda.xsh
no change     /Users/jkozik/miniforge3/etc/profile.d/conda.csh
modified      /Users/jkozik/.zshrc

==> For changes to take effect, close and re-open your current shell. <==

Running éshell inité, which:
 - modifies RC file: "/Users/jkozik/.zshrc"
 - generates config for root prefix: "/Users/jkozik/miniforge3"
 - sets mamba executable to: "/Users/jkozik/miniforge3/bin/mamba"
The following has been added in your "/Users/jkozik/.zshrc" file

Running `shell init`, which:
 - modifies RC file: "/Users/jkozik/.zshrc"
 - generates config for root prefix: "/Users/jkozik/miniforge3"
 - sets mamba executable to: "/Users/jkozik/miniforge3/bin/mamba"
The following has been added in your "/Users/jkozik/.zshrc" file

# >>> mamba initialize >>>
# !! Contents within this block are managed by 'mamba shell init' !!
export MAMBA_EXE='/Users/jkozik/miniforge3/bin/mamba';
export MAMBA_ROOT_PREFIX='/Users/jkozik/miniforge3';
__mamba_setup="$("$MAMBA_EXE" shell hook --shell zsh --root-prefix "$MAMBA_ROOT_PREFIX" 2> /dev/null)"
if [ $? -eq 0 ]; then
    eval "$__mamba_setup"
else
    alias mamba="$MAMBA_EXE"  # Fallback on help from mamba activate
fi
unset __mamba_setup
# <<< mamba initialize <<<

Thank you for installing Miniforge3!
jkozik@Jacks-Mac-mini ~ %    
```
