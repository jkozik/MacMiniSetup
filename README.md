# MacMiniSetup
Notes on getting Mac Mini M4 setup with VSCode for remote access.  Includes AI tools.

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
 . . . editted 100s of lines of installation messages

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
## Verify
Log out, log back in and verify some basics. Verify that the "base" shows in the prompt.  Also verify that python works through the miniforge local path. 
```
(base) jkozik@Jacks-Mac-mini ~ % where python
/Users/jkozik/miniforge3/bin/python
(base) jkozik@Jacks-Mac-mini ~ % python --version
Python 3.12.9
(base) jkozik@Jacks-Mac-mini ~ %
```
I am showing this detail because, I did this myself incorrectly.  Don't forget to say `yes` above.  The default python packages don't always work and conda environments, or other local venv-like environments, are needed. 
# Setup VSCode Remote
To make sure that everything is setup correctly, open up VSCode remotely.  From the home directory, install Jupyter Notebook extension.
![image](https://github.com/user-attachments/assets/fae69cbb-5f19-4acc-86c5-2f9a48f15218)
Then in a project folder, create an empty .ipynb file. VScode will recognize that this is a jupyter notebook and prompt to install python extension.

![image](https://github.com/user-attachments/assets/767ff1b4-09c5-4dd2-b722-f2f65dcd4655)

In the upper right of the vscode scren, there's a Select Kernal button.  VSCode will prompt for what environment to run.  Look for the one with conda in the path.
![image](https://github.com/user-attachments/assets/91050e87-0465-4308-b1d8-e0e0f68e844a)
Next try a simple arithmetic operation, 1+1, in the `Code` section.  Note:  VSCode will prompt to install a kernal package.  This is normal.

![image](https://github.com/user-attachments/assets/f3f86573-fb8c-4249-a5b5-c11e1065b27b)

After the install, the notebook will show a result

![image](https://github.com/user-attachments/assets/49c6b366-0fda-407a-983f-598410ce3e85)

I am showing this step, because I tried to install VSCode extensions in a subfolder.  That doesn't always work and in the case of jupyter notebooks, it definitely does not work.  My problem was that it was failing silently and I was cluelessly trying things when was really not that difficult. 

## Setup a conda environment for Python 3.8
To use Pytorch, the current version of Python wont work on Apple Silicon.  (So I am told).  Thus conda is used to setup an environment a Python 3.8 environment.  
```
(base) jkozik@Jacks-Mac-mini ~ % cd projects
(base) jkozik@Jacks-Mac-mini projects % cd MacMiniSetup
(base) jkozik@Jacks-Mac-mini MacMiniSetup % conda create --prefix ./env python=3.8
Channels:
 - conda-forge
Platform: osx-arm64
Collecting package metadata (repodata.json): done
Solving environment: done

## Package Plan ##

  environment location: /Users/jkozik/projects/MacMiniSetup/env

  added / updated specs:
    - python=3.8


The following NEW packages will be INSTALLED:

  bzip2              conda-forge/osx-arm64::bzip2-1.0.8-h99b78c6_7
  ca-certificates    conda-forge/noarch::ca-certificates-2025.4.26-hbd8a1cb_0
  libffi             conda-forge/osx-arm64::libffi-3.4.6-h1da3d7d_1
  liblzma            conda-forge/osx-arm64::liblzma-5.8.1-h39f12f2_0
  liblzma-devel      conda-forge/osx-arm64::liblzma-devel-5.8.1-h39f12f2_0
  libsqlite          conda-forge/osx-arm64::libsqlite-3.49.1-h3f77e49_2
  libzlib            conda-forge/osx-arm64::libzlib-1.3.1-h8359307_2
  ncurses            conda-forge/osx-arm64::ncurses-6.5-h5e97a16_3
  openssl            conda-forge/osx-arm64::openssl-3.5.0-h81ee809_0
  pip                conda-forge/noarch::pip-24.3.1-pyh8b19718_0
  python             conda-forge/osx-arm64::python-3.8.20-h7d35d02_2_cpython
  readline           conda-forge/osx-arm64::readline-8.2-h1d1bf99_2
  setuptools         conda-forge/noarch::setuptools-75.3.0-pyhd8ed1ab_0
  tk                 conda-forge/osx-arm64::tk-8.6.13-h5083fa2_1
  wheel              conda-forge/noarch::wheel-0.45.1-pyhd8ed1ab_0
  xz                 conda-forge/osx-arm64::xz-5.8.1-h9a6d368_0
  xz-gpl-tools       conda-forge/osx-arm64::xz-gpl-tools-5.8.1-h9a6d368_0
  xz-tools           conda-forge/osx-arm64::xz-tools-5.8.1-h39f12f2_0


Proceed ([y]/n)? y


Downloading and Extracting Packages:

Preparing transaction: done
Verifying transaction: done
Executing transaction: done
#
# To activate this environment, use
#
#     $ conda activate /Users/jkozik/projects/MacMiniSetup/env
#
# To deactivate an active environment, use
#
#     $ conda deactivate

(base) jkozik@Jacks-Mac-mini MacMiniSetup % conda activate /Users/jkozik/projects/MacMiniSetup/env
(/Users/jkozik/projects/MacMiniSetup/env) jkozik@Jacks-Mac-mini MacMiniSetup %
```
This environment is installed just for this project directory.  Whenever this project is being worked, the conda environment needs to be activated.  The manual command line is nice and straight forward.  When you get into VSCode, it will see the environment in the current folder and also all the other environments defined for the account.  

## Update VSCode Kernal to point to new environment
Look at the VSCode screen and select the base enviroment on the upper right.
![image](https://github.com/user-attachments/assets/33d1e312-4fd0-4d6f-a9bd-8bb0e305a123)

Then Select Another Kernal->Python Environments->env/bin/Python
![image](https://github.com/user-attachments/assets/6d4b76ac-1fe1-494b-8694-044cf801ee37)

# Install Pytorch
In the special conda environment, install the pytorch packages using pip install
```
(/Users/jkozik/projects/MacMiniSetup/env) jkozik@Jacks-Mac-mini MacMiniSetup % pip3 install torch torchvision torchaudio
Collecting torch
  Downloading torch-2.4.1-cp38-none-macosx_11_0_arm64.whl.metadata (26 kB)
Collecting torchvision
  Downloading torchvision-0.19.1-cp38-cp38-macosx_11_0_arm64.whl.metadata (6.0 kB)
Collecting torchaudio
  Downloading torchaudio-2.4.1-cp38-cp38-macosx_11_0_arm64.whl.metadata (6.4 kB)
Collecting filelock (from torch)
  Downloading filelock-3.16.1-py3-none-any.whl.metadata (2.9 kB)
Collecting typing-extensions>=4.8.0 (from torch)
  Downloading typing_extensions-4.13.2-py3-none-any.whl.metadata (3.0 kB)
Collecting sympy (from torch)
  Downloading sympy-1.13.3-py3-none-any.whl.metadata (12 kB)
Collecting networkx (from torch)
  Downloading networkx-3.1-py3-none-any.whl.metadata (5.3 kB)
Collecting jinja2 (from torch)
  Downloading jinja2-3.1.6-py3-none-any.whl.metadata (2.9 kB)
Collecting fsspec (from torch)
  Downloading fsspec-2025.3.0-py3-none-any.whl.metadata (11 kB)
Collecting numpy (from torchvision)
  Downloading numpy-1.24.4-cp38-cp38-macosx_11_0_arm64.whl.metadata (5.6 kB)
Collecting pillow!=8.3.*,>=5.3.0 (from torchvision)
  Downloading pillow-10.4.0-cp38-cp38-macosx_11_0_arm64.whl.metadata (9.2 kB)
Collecting MarkupSafe>=2.0 (from jinja2->torch)
  Downloading MarkupSafe-2.1.5-cp38-cp38-macosx_10_9_universal2.whl.metadata (3.0 kB)
Collecting mpmath<1.4,>=1.1.0 (from sympy->torch)
  Downloading mpmath-1.3.0-py3-none-any.whl.metadata (8.6 kB)
Downloading torch-2.4.1-cp38-none-macosx_11_0_arm64.whl (62.1 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 62.1/62.1 MB 16.6 MB/s eta 0:00:00
Downloading torchvision-0.19.1-cp38-cp38-macosx_11_0_arm64.whl (1.7 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.7/1.7 MB 14.4 MB/s eta 0:00:00
Downloading torchaudio-2.4.1-cp38-cp38-macosx_11_0_arm64.whl (1.8 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.8/1.8 MB 14.9 MB/s eta 0:00:00
Downloading pillow-10.4.0-cp38-cp38-macosx_11_0_arm64.whl (3.4 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 3.4/3.4 MB 16.0 MB/s eta 0:00:00
Downloading typing_extensions-4.13.2-py3-none-any.whl (45 kB)
Downloading filelock-3.16.1-py3-none-any.whl (16 kB)
Downloading fsspec-2025.3.0-py3-none-any.whl (193 kB)
Downloading jinja2-3.1.6-py3-none-any.whl (134 kB)
Downloading networkx-3.1-py3-none-any.whl (2.1 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 2.1/2.1 MB 20.3 MB/s eta 0:00:00
Downloading numpy-1.24.4-cp38-cp38-macosx_11_0_arm64.whl (13.8 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 13.8/13.8 MB 17.7 MB/s eta 0:00:00
Downloading sympy-1.13.3-py3-none-any.whl (6.2 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6.2/6.2 MB 16.2 MB/s eta 0:00:00
Downloading MarkupSafe-2.1.5-cp38-cp38-macosx_10_9_universal2.whl (18 kB)
Downloading mpmath-1.3.0-py3-none-any.whl (536 kB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 536.2/536.2 kB 10.3 MB/s eta 0:00:00
Installing collected packages: mpmath, typing-extensions, sympy, pillow, numpy, networkx, MarkupSafe, fsspec, filelock, jinja2, torch, torchvision, torchaudio
Successfully installed MarkupSafe-2.1.5 filelock-3.16.1 fsspec-2025.3.0 jinja2-3.1.6 mpmath-1.3.0 networkx-3.1 numpy-1.24.4 pillow-10.4.0 sympy-1.13.3 torch-2.4.1 torchaudio-2.4.1 torchvision-0.19.1 typing-extensions-4.13.2
(/Users/jkozik/projects/MacMiniSetup/env) jkozik@Jacks-Mac-mini MacMiniSetup %
```
These packages are installed just for this project directory, enabled by this particular conda environment.  After I learned how this worked, I realized this is a distant cousin of docker containers.  For all the version dependencies that live in the python package world mean that you need unique, isolated, environments per project. I continue to learn that there are several environment managers for python and slightly different choices available for the MacOS world. 
## Also some data packages
```
(/Users/jkozik/projects/MacMiniSetup/env) jkozik@Jacks-Mac-mini MacMiniSetup % conda install jupyter pandas numpy matplotlib scikit-learn tqdm
Channels:
 - conda-forge
Platform: osx-arm64
Collecting package metadata (repodata.json): done
Solving environment: done

## Package Plan ##

  environment location: /Users/jkozik/projects/MacMiniSetup/env

  added / updated specs:
    - jupyter
    - matplotlib
    - numpy
    - pandas
    - scikit-learn
    - tqdm


The following packages will be downloaded:

    package                    |            build
    ---------------------------|-----------------
    anyio-3.7.1                |     pyhd8ed1ab_0          94 KB  conda-forge
    appnope-0.1.4              |     pyhd8ed1ab_0          10 KB  conda-forge
    argon2-cffi-23.1.0         |     pyhd8ed1ab_0          18 KB  conda-forge
    argon2-cffi-bindings-21.2.0|   py38hb192615_4          33 KB  conda-forge
    arrow-1.3.0                |     pyhd8ed1ab_0          98 KB  conda-forge
    asttokens-3.0.0            |     pyhd8ed1ab_0          27 KB  conda-forge
    async-lru-2.0.4            |     pyhd8ed1ab_0          15 KB  conda-forge
    attrs-24.2.0               |     pyh71513ae_0          55 KB  conda-forge
    babel-2.16.0               |     pyhd8ed1ab_0         6.2 MB  conda-forge
    backcall-0.2.0             |     pyh9f0ad1d_0          13 KB  conda-forge
    beautifulsoup4-4.12.3      |     pyha770c72_0         115 KB  conda-forge
    bleach-6.1.0               |     pyhd8ed1ab_0         128 KB  conda-forge
    brotli-1.1.0               |       hd74edd7_2          19 KB  conda-forge
    brotli-bin-1.1.0           |       hd74edd7_2          16 KB  conda-forge
    brotli-python-1.0.9        |   py38h2b1e499_8         365 KB  conda-forge
    cached-property-1.5.2      |       hd8ed1ab_1           4 KB  conda-forge
    cached_property-1.5.2      |     pyha770c72_1          11 KB  conda-forge
    certifi-2024.8.30          |     pyhd8ed1ab_0         160 KB  conda-forge
    cffi-1.17.0                |   py38h858044d_0         223 KB  conda-forge
    charset-normalizer-3.4.0   |     pyhd8ed1ab_0          46 KB  conda-forge
    colorama-0.4.6             |     pyhd8ed1ab_0          25 KB  conda-forge
    comm-0.2.2                 |     pyhd8ed1ab_0          12 KB  conda-forge
    contourpy-1.1.1            |   py38h9afee92_1         212 KB  conda-forge
    cycler-0.12.1              |     pyhd8ed1ab_0          13 KB  conda-forge
    debugpy-1.8.5              |   py38h11842c7_0         1.8 MB  conda-forge
    decorator-5.1.1            |     pyhd8ed1ab_0          12 KB  conda-forge
    defusedxml-0.7.1           |     pyhd8ed1ab_0          23 KB  conda-forge
    entrypoints-0.4            |     pyhd8ed1ab_0           9 KB  conda-forge
    exceptiongroup-1.2.2       |     pyhd8ed1ab_0          20 KB  conda-forge
    executing-2.1.0            |     pyhd8ed1ab_0          28 KB  conda-forge
    fonttools-4.53.1           |   py38h3237794_0         2.1 MB  conda-forge
    fqdn-1.5.1                 |     pyhd8ed1ab_0          14 KB  conda-forge
    freetype-2.13.3            |       hce30654_1         168 KB  conda-forge
    h11-0.14.0                 |     pyhd8ed1ab_0          47 KB  conda-forge
    h2-4.1.0                   |     pyhd8ed1ab_0          46 KB  conda-forge
    hpack-4.0.0                |     pyh9f0ad1d_0          25 KB  conda-forge
    httpcore-1.0.7             |     pyh29332c3_1          48 KB  conda-forge
    httpx-0.27.2               |     pyhd8ed1ab_0          64 KB  conda-forge
    hyperframe-6.0.1           |     pyhd8ed1ab_0          14 KB  conda-forge
    idna-3.10                  |     pyhd8ed1ab_0          49 KB  conda-forge
    importlib-metadata-8.5.0   |     pyha770c72_0          28 KB  conda-forge
    importlib-resources-6.4.5  |     pyhd8ed1ab_0           9 KB  conda-forge
    importlib_metadata-8.5.0   |       hd8ed1ab_1           9 KB  conda-forge
    importlib_resources-6.4.5  |     pyhd8ed1ab_0          32 KB  conda-forge
    ipython-8.12.2             |     pyhd1c38e8_0         571 KB  conda-forge
    ipywidgets-8.1.5           |     pyhd8ed1ab_0         111 KB  conda-forge
    isoduration-20.11.0        |     pyhd8ed1ab_0          17 KB  conda-forge
    jedi-0.19.1                |     pyhd8ed1ab_0         822 KB  conda-forge
    jinja2-3.1.4               |     pyhd8ed1ab_0         109 KB  conda-forge
    joblib-1.4.2               |     pyhd8ed1ab_0         215 KB  conda-forge
    json5-0.9.25               |     pyhd8ed1ab_0          27 KB  conda-forge
    jsonpointer-3.0.0          |   py38h10201cd_0          16 KB  conda-forge
    jsonschema-4.23.0          |     pyhd8ed1ab_0          73 KB  conda-forge
    jsonschema-specifications-2024.10.1|     pyhd8ed1ab_0          16 KB  conda-forge
    jsonschema-with-format-nongpl-4.23.0|       hd8ed1ab_1           7 KB  conda-forge
    jupyter-1.1.1              |     pyhd8ed1ab_0           9 KB  conda-forge
    jupyter-lsp-2.2.5          |     pyhd8ed1ab_0          54 KB  conda-forge
    jupyter_client-8.6.3       |     pyhd8ed1ab_0         104 KB  conda-forge
    jupyter_console-6.6.3      |     pyhd8ed1ab_0          26 KB  conda-forge
    jupyter_events-0.10.0      |     pyhd8ed1ab_0          21 KB  conda-forge
    jupyter_server-2.7.0       |     pyhd8ed1ab_0         308 KB  conda-forge
    jupyter_server_terminals-0.5.3|     pyhd8ed1ab_0          19 KB  conda-forge
    jupyterlab-4.2.5           |     pyhd8ed1ab_0         7.0 MB  conda-forge
    jupyterlab_pygments-0.3.0  |     pyhd8ed1ab_1          18 KB  conda-forge
    jupyterlab_server-2.27.3   |     pyhd8ed1ab_0          48 KB  conda-forge
    jupyterlab_widgets-3.0.13  |     pyhd8ed1ab_0         182 KB  conda-forge
    kiwisolver-1.4.5           |   py38h9afee92_1          61 KB  conda-forge
    lcms2-2.17                 |       h7eeda09_0         207 KB  conda-forge
    lerc-4.0.0                 |       hd64df32_1         184 KB  conda-forge
    libblas-3.9.0              |20_osxarm64_openblas          14 KB  conda-forge
    libbrotlicommon-1.1.0      |       hd74edd7_2          67 KB  conda-forge
    libbrotlidec-1.1.0         |       hd74edd7_2          28 KB  conda-forge
    libbrotlienc-1.1.0         |       hd74edd7_2         273 KB  conda-forge
    libcblas-3.9.0             |20_osxarm64_openblas          14 KB  conda-forge
    libcxx-20.1.4              |       ha82da77_0         553 KB  conda-forge
    libdeflate-1.23            |       h5773f1b_0          53 KB  conda-forge
    libfreetype-2.13.3         |       hce30654_1           8 KB  conda-forge
    libfreetype6-2.13.3        |       h1d14073_1         326 KB  conda-forge
    libgfortran-14.2.0         |     heb5dd2a_105         152 KB  conda-forge
    libgfortran5-14.2.0        |     h2c44a93_105         787 KB  conda-forge
    libjpeg-turbo-3.1.0        |       h5505292_0         541 KB  conda-forge
    liblapack-3.9.0            |20_osxarm64_openblas          14 KB  conda-forge
    libopenblas-0.3.25         |openmp_h6c19121_0         2.8 MB  conda-forge
    libpng-1.6.47              |       h3783ad8_0         253 KB  conda-forge
    libsodium-1.0.18           |       h27ca646_1         317 KB  conda-forge
    libtiff-4.7.0              |       h551f018_4         362 KB  conda-forge
    libwebp-base-1.5.0         |       h2471fea_0         283 KB  conda-forge
    libxcb-1.17.0              |       hdb1d25a_0         316 KB  conda-forge
    llvm-openmp-20.1.4         |       hdb05f8b_0         276 KB  conda-forge
    markupsafe-2.1.5           |   py38h336bac9_0          23 KB  conda-forge
    matplotlib-3.7.3           |   py38h150bfb4_0           8 KB  conda-forge
    matplotlib-base-3.7.3      |   py38hef9d0d7_0         6.3 MB  conda-forge
    matplotlib-inline-0.1.7    |     pyhd8ed1ab_0          14 KB  conda-forge
    mistune-3.0.2              |     pyhd8ed1ab_0          64 KB  conda-forge
    munkres-1.1.4              |     pyh9f0ad1d_0          12 KB  conda-forge
    nbclient-0.10.2            |     pyhd8ed1ab_0          27 KB  conda-forge
    nbconvert-core-7.16.4      |     pyhff2d567_2         184 KB  conda-forge
    nbformat-5.10.4            |     pyhd8ed1ab_0          99 KB  conda-forge
    nest-asyncio-1.6.0         |     pyhd8ed1ab_0          11 KB  conda-forge
    notebook-7.2.2             |     pyhd8ed1ab_0         3.7 MB  conda-forge
    notebook-shim-0.2.4        |     pyhd8ed1ab_0          16 KB  conda-forge
    numpy-1.24.4               |   py38ha84db1f_0         5.3 MB  conda-forge
    openjpeg-2.5.3             |       h8a3d83b_0         312 KB  conda-forge
    overrides-7.7.0            |     pyhd8ed1ab_0          30 KB  conda-forge
    packaging-25.0             |     pyh29332c3_1          61 KB  conda-forge
    pandas-2.0.3               |   py38hefb543e_1        11.0 MB  conda-forge
    pandocfilters-1.5.0        |     pyhd8ed1ab_0          11 KB  conda-forge
    parso-0.8.4                |     pyhd8ed1ab_0          73 KB  conda-forge
    pexpect-4.9.0              |     pyhd8ed1ab_0          52 KB  conda-forge
    pickleshare-0.7.5          |          py_1003           9 KB  conda-forge
    pillow-10.4.0              |   py38h2c6aaed_0        40.2 MB  conda-forge
    pkgutil-resolve-name-1.3.10|     pyhd8ed1ab_1          11 KB  conda-forge
    platformdirs-4.3.6         |     pyhd8ed1ab_0          20 KB  conda-forge
    pooch-1.8.2                |     pyhd8ed1ab_0          53 KB  conda-forge
    prometheus_client-0.21.0   |     pyhd8ed1ab_0          48 KB  conda-forge
    prompt-toolkit-3.0.48      |     pyha770c72_0         264 KB  conda-forge
    prompt_toolkit-3.0.48      |       hd8ed1ab_1           6 KB  conda-forge
    psutil-6.0.0               |   py38h3237794_0         366 KB  conda-forge
    pthread-stubs-0.4          |    hd74edd7_1002           8 KB  conda-forge
    ptyprocess-0.7.0           |     pyhd3deb0d_0          16 KB  conda-forge
    pure_eval-0.2.3            |     pyhd8ed1ab_0          16 KB  conda-forge
    pycparser-2.22             |     pyhd8ed1ab_0         103 KB  conda-forge
    pygments-2.18.0            |     pyhd8ed1ab_0         859 KB  conda-forge
    pyparsing-3.1.4            |     pyhd8ed1ab_0          88 KB  conda-forge
    pysocks-1.7.1              |     pyha2e5f31_6          19 KB  conda-forge
    python-dateutil-2.9.0      |     pyhd8ed1ab_0         218 KB  conda-forge
    python-fastjsonschema-2.20.0|     pyhd8ed1ab_0         221 KB  conda-forge
    python-json-logger-2.0.7   |     pyhd8ed1ab_0          13 KB  conda-forge
    python-tzdata-2024.2       |     pyhd8ed1ab_0         139 KB  conda-forge
    python_abi-3.8             |           7_cp38           7 KB  conda-forge
    pytz-2024.2                |     pyhd8ed1ab_0         183 KB  conda-forge
    pyyaml-6.0.2               |   py38h3237794_0         158 KB  conda-forge
    pyzmq-26.2.0               |   py38h7e0d939_0         306 KB  conda-forge
    referencing-0.35.1         |     pyhd8ed1ab_0          41 KB  conda-forge
    requests-2.32.3            |     pyhd8ed1ab_0          57 KB  conda-forge
    rfc3339-validator-0.1.4    |     pyhd8ed1ab_0           8 KB  conda-forge
    rfc3986-validator-0.1.1    |     pyh9f0ad1d_0           8 KB  conda-forge
    rpds-py-0.20.0             |   py38h186058e_0         285 KB  conda-forge
    scikit-learn-1.3.2         |   py38he1bc1c9_2         7.1 MB  conda-forge
    scipy-1.10.1               |   py38h038e806_3        13.5 MB  conda-forge
    send2trash-1.8.0           |     pyhd8ed1ab_0          17 KB  conda-forge
    six-1.16.0                 |     pyh6c4a22f_0          14 KB  conda-forge
    sniffio-1.3.1              |     pyhd8ed1ab_0          15 KB  conda-forge
    soupsieve-2.5              |     pyhd8ed1ab_1          36 KB  conda-forge
    stack_data-0.6.2           |     pyhd8ed1ab_0          26 KB  conda-forge
    terminado-0.18.1           |     pyh31c8845_0          22 KB  conda-forge
    threadpoolctl-3.5.0        |     pyhc1e730c_0          23 KB  conda-forge
    tinycss2-1.4.0             |     pyhd8ed1ab_0          28 KB  conda-forge
    tomli-2.0.2                |     pyhd8ed1ab_0          18 KB  conda-forge
    tornado-6.4.1              |   py38h3237794_0         627 KB  conda-forge
    tqdm-4.67.1                |     pyhd8ed1ab_0          87 KB  conda-forge
    traitlets-5.14.3           |     pyhd8ed1ab_0         108 KB  conda-forge
    types-python-dateutil-2.9.0.20241003|     pyhff2d567_0          21 KB  conda-forge
    typing-extensions-4.12.2   |       hd8ed1ab_0          10 KB  conda-forge
    typing_extensions-4.12.2   |     pyha770c72_0          39 KB  conda-forge
    typing_utils-0.1.0         |     pyhd8ed1ab_0          14 KB  conda-forge
    unicodedata2-15.1.0        |   py38hb192615_0         368 KB  conda-forge
    uri-template-1.3.0         |     pyhd8ed1ab_0          23 KB  conda-forge
    urllib3-2.2.3              |     pyhd8ed1ab_0          96 KB  conda-forge
    wcwidth-0.2.13             |     pyhd8ed1ab_0          32 KB  conda-forge
    webcolors-24.8.0           |     pyhd8ed1ab_0          18 KB  conda-forge
    webencodings-0.5.1         |     pyhd8ed1ab_2          15 KB  conda-forge
    websocket-client-1.8.0     |     pyhd8ed1ab_0          46 KB  conda-forge
    widgetsnbextension-4.0.13  |     pyhd8ed1ab_0         878 KB  conda-forge
    xorg-libxau-1.0.12         |       h5505292_0          13 KB  conda-forge
    xorg-libxdmcp-1.1.5        |       hd74edd7_0          18 KB  conda-forge
    yaml-0.2.5                 |       h3422bc3_2          86 KB  conda-forge
    zeromq-4.3.5               |       hcc0f68c_4         292 KB  conda-forge
    zipp-3.21.0                |     pyhd8ed1ab_0          21 KB  conda-forge
    zstandard-0.19.0           |   py38hb991d35_0         555 KB  conda-forge
    ------------------------------------------------------------
                                           Total:       125.0 MB

The following NEW packages will be INSTALLED:

  anyio              conda-forge/noarch::anyio-3.7.1-pyhd8ed1ab_0
  appnope            conda-forge/noarch::appnope-0.1.4-pyhd8ed1ab_0
  argon2-cffi        conda-forge/noarch::argon2-cffi-23.1.0-pyhd8ed1ab_0
  argon2-cffi-bindi~ conda-forge/osx-arm64::argon2-cffi-bindings-21.2.0-py38hb192615_4
  arrow              conda-forge/noarch::arrow-1.3.0-pyhd8ed1ab_0
  asttokens          conda-forge/noarch::asttokens-3.0.0-pyhd8ed1ab_0
  async-lru          conda-forge/noarch::async-lru-2.0.4-pyhd8ed1ab_0
  attrs              conda-forge/noarch::attrs-24.2.0-pyh71513ae_0
  babel              conda-forge/noarch::babel-2.16.0-pyhd8ed1ab_0
  backcall           conda-forge/noarch::backcall-0.2.0-pyh9f0ad1d_0
  beautifulsoup4     conda-forge/noarch::beautifulsoup4-4.12.3-pyha770c72_0
  bleach             conda-forge/noarch::bleach-6.1.0-pyhd8ed1ab_0
  brotli             conda-forge/osx-arm64::brotli-1.1.0-hd74edd7_2
  brotli-bin         conda-forge/osx-arm64::brotli-bin-1.1.0-hd74edd7_2
  brotli-python      conda-forge/osx-arm64::brotli-python-1.0.9-py38h2b1e499_8
  cached-property    conda-forge/noarch::cached-property-1.5.2-hd8ed1ab_1
  cached_property    conda-forge/noarch::cached_property-1.5.2-pyha770c72_1
  certifi            conda-forge/noarch::certifi-2024.8.30-pyhd8ed1ab_0
  cffi               conda-forge/osx-arm64::cffi-1.17.0-py38h858044d_0
  charset-normalizer conda-forge/noarch::charset-normalizer-3.4.0-pyhd8ed1ab_0
  colorama           conda-forge/noarch::colorama-0.4.6-pyhd8ed1ab_0
  comm               conda-forge/noarch::comm-0.2.2-pyhd8ed1ab_0
  contourpy          conda-forge/osx-arm64::contourpy-1.1.1-py38h9afee92_1
  cycler             conda-forge/noarch::cycler-0.12.1-pyhd8ed1ab_0
  debugpy            conda-forge/osx-arm64::debugpy-1.8.5-py38h11842c7_0
  decorator          conda-forge/noarch::decorator-5.1.1-pyhd8ed1ab_0
  defusedxml         conda-forge/noarch::defusedxml-0.7.1-pyhd8ed1ab_0
  entrypoints        conda-forge/noarch::entrypoints-0.4-pyhd8ed1ab_0
  exceptiongroup     conda-forge/noarch::exceptiongroup-1.2.2-pyhd8ed1ab_0
  executing          conda-forge/noarch::executing-2.1.0-pyhd8ed1ab_0
  fonttools          conda-forge/osx-arm64::fonttools-4.53.1-py38h3237794_0
  fqdn               conda-forge/noarch::fqdn-1.5.1-pyhd8ed1ab_0
  freetype           conda-forge/osx-arm64::freetype-2.13.3-hce30654_1
  h11                conda-forge/noarch::h11-0.14.0-pyhd8ed1ab_0
  h2                 conda-forge/noarch::h2-4.1.0-pyhd8ed1ab_0
  hpack              conda-forge/noarch::hpack-4.0.0-pyh9f0ad1d_0
  httpcore           conda-forge/noarch::httpcore-1.0.7-pyh29332c3_1
  httpx              conda-forge/noarch::httpx-0.27.2-pyhd8ed1ab_0
  hyperframe         conda-forge/noarch::hyperframe-6.0.1-pyhd8ed1ab_0
  idna               conda-forge/noarch::idna-3.10-pyhd8ed1ab_0
  importlib-metadata conda-forge/noarch::importlib-metadata-8.5.0-pyha770c72_0
  importlib-resourc~ conda-forge/noarch::importlib-resources-6.4.5-pyhd8ed1ab_0
  importlib_metadata conda-forge/noarch::importlib_metadata-8.5.0-hd8ed1ab_1
  importlib_resourc~ conda-forge/noarch::importlib_resources-6.4.5-pyhd8ed1ab_0
  ipykernel          conda-forge/noarch::ipykernel-6.29.5-pyh57ce528_0
  ipython            conda-forge/noarch::ipython-8.12.2-pyhd1c38e8_0
  ipywidgets         conda-forge/noarch::ipywidgets-8.1.5-pyhd8ed1ab_0
  isoduration        conda-forge/noarch::isoduration-20.11.0-pyhd8ed1ab_0
  jedi               conda-forge/noarch::jedi-0.19.1-pyhd8ed1ab_0
  jinja2             conda-forge/noarch::jinja2-3.1.4-pyhd8ed1ab_0
  joblib             conda-forge/noarch::joblib-1.4.2-pyhd8ed1ab_0
  json5              conda-forge/noarch::json5-0.9.25-pyhd8ed1ab_0
  jsonpointer        conda-forge/osx-arm64::jsonpointer-3.0.0-py38h10201cd_0
  jsonschema         conda-forge/noarch::jsonschema-4.23.0-pyhd8ed1ab_0
  jsonschema-specif~ conda-forge/noarch::jsonschema-specifications-2024.10.1-pyhd8ed1ab_0
  jsonschema-with-f~ conda-forge/noarch::jsonschema-with-format-nongpl-4.23.0-hd8ed1ab_1
  jupyter            conda-forge/noarch::jupyter-1.1.1-pyhd8ed1ab_0
  jupyter-lsp        conda-forge/noarch::jupyter-lsp-2.2.5-pyhd8ed1ab_0
  jupyter_client     conda-forge/noarch::jupyter_client-8.6.3-pyhd8ed1ab_0
  jupyter_console    conda-forge/noarch::jupyter_console-6.6.3-pyhd8ed1ab_0
  jupyter_core       conda-forge/noarch::jupyter_core-5.7.2-pyh31011fe_1
  jupyter_events     conda-forge/noarch::jupyter_events-0.10.0-pyhd8ed1ab_0
  jupyter_server     conda-forge/noarch::jupyter_server-2.7.0-pyhd8ed1ab_0
  jupyter_server_te~ conda-forge/noarch::jupyter_server_terminals-0.5.3-pyhd8ed1ab_0
  jupyterlab         conda-forge/noarch::jupyterlab-4.2.5-pyhd8ed1ab_0
  jupyterlab_pygmen~ conda-forge/noarch::jupyterlab_pygments-0.3.0-pyhd8ed1ab_1
  jupyterlab_server  conda-forge/noarch::jupyterlab_server-2.27.3-pyhd8ed1ab_0
  jupyterlab_widgets conda-forge/noarch::jupyterlab_widgets-3.0.13-pyhd8ed1ab_0
  kiwisolver         conda-forge/osx-arm64::kiwisolver-1.4.5-py38h9afee92_1
  krb5               conda-forge/osx-arm64::krb5-1.21.3-h237132a_0
  lcms2              conda-forge/osx-arm64::lcms2-2.17-h7eeda09_0
  lerc               conda-forge/osx-arm64::lerc-4.0.0-hd64df32_1
  libblas            conda-forge/osx-arm64::libblas-3.9.0-20_osxarm64_openblas
  libbrotlicommon    conda-forge/osx-arm64::libbrotlicommon-1.1.0-hd74edd7_2
  libbrotlidec       conda-forge/osx-arm64::libbrotlidec-1.1.0-hd74edd7_2
  libbrotlienc       conda-forge/osx-arm64::libbrotlienc-1.1.0-hd74edd7_2
  libcblas           conda-forge/osx-arm64::libcblas-3.9.0-20_osxarm64_openblas
  libcxx             conda-forge/osx-arm64::libcxx-20.1.4-ha82da77_0
  libdeflate         conda-forge/osx-arm64::libdeflate-1.23-h5773f1b_0
  libedit            conda-forge/osx-arm64::libedit-3.1.20250104-pl5321hafb1f1b_0
  libfreetype        conda-forge/osx-arm64::libfreetype-2.13.3-hce30654_1
  libfreetype6       conda-forge/osx-arm64::libfreetype6-2.13.3-h1d14073_1
  libgfortran        conda-forge/osx-arm64::libgfortran-14.2.0-heb5dd2a_105
  libgfortran5       conda-forge/osx-arm64::libgfortran5-14.2.0-h2c44a93_105
  libjpeg-turbo      conda-forge/osx-arm64::libjpeg-turbo-3.1.0-h5505292_0
  liblapack          conda-forge/osx-arm64::liblapack-3.9.0-20_osxarm64_openblas
  libopenblas        conda-forge/osx-arm64::libopenblas-0.3.25-openmp_h6c19121_0
  libpng             conda-forge/osx-arm64::libpng-1.6.47-h3783ad8_0
  libsodium          conda-forge/osx-arm64::libsodium-1.0.18-h27ca646_1
  libtiff            conda-forge/osx-arm64::libtiff-4.7.0-h551f018_4
  libwebp-base       conda-forge/osx-arm64::libwebp-base-1.5.0-h2471fea_0
  libxcb             conda-forge/osx-arm64::libxcb-1.17.0-hdb1d25a_0
  llvm-openmp        conda-forge/osx-arm64::llvm-openmp-20.1.4-hdb05f8b_0
  markupsafe         conda-forge/osx-arm64::markupsafe-2.1.5-py38h336bac9_0
  matplotlib         conda-forge/osx-arm64::matplotlib-3.7.3-py38h150bfb4_0
  matplotlib-base    conda-forge/osx-arm64::matplotlib-base-3.7.3-py38hef9d0d7_0
  matplotlib-inline  conda-forge/noarch::matplotlib-inline-0.1.7-pyhd8ed1ab_0
  mistune            conda-forge/noarch::mistune-3.0.2-pyhd8ed1ab_0
  munkres            conda-forge/noarch::munkres-1.1.4-pyh9f0ad1d_0
  nbclient           conda-forge/noarch::nbclient-0.10.2-pyhd8ed1ab_0
  nbconvert-core     conda-forge/noarch::nbconvert-core-7.16.4-pyhff2d567_2
  nbformat           conda-forge/noarch::nbformat-5.10.4-pyhd8ed1ab_0
  nest-asyncio       conda-forge/noarch::nest-asyncio-1.6.0-pyhd8ed1ab_0
  notebook           conda-forge/noarch::notebook-7.2.2-pyhd8ed1ab_0
  notebook-shim      conda-forge/noarch::notebook-shim-0.2.4-pyhd8ed1ab_0
  numpy              conda-forge/osx-arm64::numpy-1.24.4-py38ha84db1f_0
  openjpeg           conda-forge/osx-arm64::openjpeg-2.5.3-h8a3d83b_0
  overrides          conda-forge/noarch::overrides-7.7.0-pyhd8ed1ab_0
  packaging          conda-forge/noarch::packaging-25.0-pyh29332c3_1
  pandas             conda-forge/osx-arm64::pandas-2.0.3-py38hefb543e_1
  pandocfilters      conda-forge/noarch::pandocfilters-1.5.0-pyhd8ed1ab_0
  parso              conda-forge/noarch::parso-0.8.4-pyhd8ed1ab_0
  pexpect            conda-forge/noarch::pexpect-4.9.0-pyhd8ed1ab_0
  pickleshare        conda-forge/noarch::pickleshare-0.7.5-py_1003
  pillow             conda-forge/osx-arm64::pillow-10.4.0-py38h2c6aaed_0
  pkgutil-resolve-n~ conda-forge/noarch::pkgutil-resolve-name-1.3.10-pyhd8ed1ab_1
  platformdirs       conda-forge/noarch::platformdirs-4.3.6-pyhd8ed1ab_0
  pooch              conda-forge/noarch::pooch-1.8.2-pyhd8ed1ab_0
  prometheus_client  conda-forge/noarch::prometheus_client-0.21.0-pyhd8ed1ab_0
  prompt-toolkit     conda-forge/noarch::prompt-toolkit-3.0.48-pyha770c72_0
  prompt_toolkit     conda-forge/noarch::prompt_toolkit-3.0.48-hd8ed1ab_1
  psutil             conda-forge/osx-arm64::psutil-6.0.0-py38h3237794_0
  pthread-stubs      conda-forge/osx-arm64::pthread-stubs-0.4-hd74edd7_1002
  ptyprocess         conda-forge/noarch::ptyprocess-0.7.0-pyhd3deb0d_0
  pure_eval          conda-forge/noarch::pure_eval-0.2.3-pyhd8ed1ab_0
  pycparser          conda-forge/noarch::pycparser-2.22-pyhd8ed1ab_0
  pygments           conda-forge/noarch::pygments-2.18.0-pyhd8ed1ab_0
  pyparsing          conda-forge/noarch::pyparsing-3.1.4-pyhd8ed1ab_0
  pysocks            conda-forge/noarch::pysocks-1.7.1-pyha2e5f31_6
  python-dateutil    conda-forge/noarch::python-dateutil-2.9.0-pyhd8ed1ab_0
  python-fastjsonsc~ conda-forge/noarch::python-fastjsonschema-2.20.0-pyhd8ed1ab_0
  python-json-logger conda-forge/noarch::python-json-logger-2.0.7-pyhd8ed1ab_0
  python-tzdata      conda-forge/noarch::python-tzdata-2024.2-pyhd8ed1ab_0
  python_abi         conda-forge/noarch::python_abi-3.8-7_cp38
  pytz               conda-forge/noarch::pytz-2024.2-pyhd8ed1ab_0
  pyyaml             conda-forge/osx-arm64::pyyaml-6.0.2-py38h3237794_0
  pyzmq              conda-forge/osx-arm64::pyzmq-26.2.0-py38h7e0d939_0
  referencing        conda-forge/noarch::referencing-0.35.1-pyhd8ed1ab_0
  requests           conda-forge/noarch::requests-2.32.3-pyhd8ed1ab_0
  rfc3339-validator  conda-forge/noarch::rfc3339-validator-0.1.4-pyhd8ed1ab_0
  rfc3986-validator  conda-forge/noarch::rfc3986-validator-0.1.1-pyh9f0ad1d_0
  rpds-py            conda-forge/osx-arm64::rpds-py-0.20.0-py38h186058e_0
  scikit-learn       conda-forge/osx-arm64::scikit-learn-1.3.2-py38he1bc1c9_2
  scipy              conda-forge/osx-arm64::scipy-1.10.1-py38h038e806_3
  send2trash         conda-forge/noarch::send2trash-1.8.0-pyhd8ed1ab_0
  six                conda-forge/noarch::six-1.16.0-pyh6c4a22f_0
  sniffio            conda-forge/noarch::sniffio-1.3.1-pyhd8ed1ab_0
  soupsieve          conda-forge/noarch::soupsieve-2.5-pyhd8ed1ab_1
  stack_data         conda-forge/noarch::stack_data-0.6.2-pyhd8ed1ab_0
  terminado          conda-forge/noarch::terminado-0.18.1-pyh31c8845_0
  threadpoolctl      conda-forge/noarch::threadpoolctl-3.5.0-pyhc1e730c_0
  tinycss2           conda-forge/noarch::tinycss2-1.4.0-pyhd8ed1ab_0
  tomli              conda-forge/noarch::tomli-2.0.2-pyhd8ed1ab_0
  tornado            conda-forge/osx-arm64::tornado-6.4.1-py38h3237794_0
  tqdm               conda-forge/noarch::tqdm-4.67.1-pyhd8ed1ab_0
  traitlets          conda-forge/noarch::traitlets-5.14.3-pyhd8ed1ab_0
  types-python-date~ conda-forge/noarch::types-python-dateutil-2.9.0.20241003-pyhff2d567_0
  typing-extensions  conda-forge/noarch::typing-extensions-4.12.2-hd8ed1ab_0
  typing_extensions  conda-forge/noarch::typing_extensions-4.12.2-pyha770c72_0
  typing_utils       conda-forge/noarch::typing_utils-0.1.0-pyhd8ed1ab_0
  unicodedata2       conda-forge/osx-arm64::unicodedata2-15.1.0-py38hb192615_0
  uri-template       conda-forge/noarch::uri-template-1.3.0-pyhd8ed1ab_0
  urllib3            conda-forge/noarch::urllib3-2.2.3-pyhd8ed1ab_0
  wcwidth            conda-forge/noarch::wcwidth-0.2.13-pyhd8ed1ab_0
  webcolors          conda-forge/noarch::webcolors-24.8.0-pyhd8ed1ab_0
  webencodings       conda-forge/noarch::webencodings-0.5.1-pyhd8ed1ab_2
  websocket-client   conda-forge/noarch::websocket-client-1.8.0-pyhd8ed1ab_0
  widgetsnbextension conda-forge/noarch::widgetsnbextension-4.0.13-pyhd8ed1ab_0
  xorg-libxau        conda-forge/osx-arm64::xorg-libxau-1.0.12-h5505292_0
  xorg-libxdmcp      conda-forge/osx-arm64::xorg-libxdmcp-1.1.5-hd74edd7_0
  yaml               conda-forge/osx-arm64::yaml-0.2.5-h3422bc3_2
  zeromq             conda-forge/osx-arm64::zeromq-4.3.5-hcc0f68c_4
  zipp               conda-forge/noarch::zipp-3.21.0-pyhd8ed1ab_0
  zstandard          conda-forge/osx-arm64::zstandard-0.19.0-py38hb991d35_0
  zstd               conda-forge/osx-arm64::zstd-1.5.7-h6491c7d_2


Proceed ([y]/n)? y


Downloading and Extracting Packages:

Preparing transaction: done
Verifying transaction: done
Executing transaction: done
(/Users/jkozik/projects/MacMiniSetup/env) jkozik@Jacks-Mac-mini MacMiniSetup %
```
I wanted to show this.  In the linux world, I would have done this with pip install and not conda install.  I don't appreciate the distinction.  Someday, I will. 
## Run benchmarks
I ran the `01_cifar10_tinyvgg.ipynb` notebood.  It ran a benchmark that trains a pytorch models on 50000 images.  On the first pass, it uses the M4's CPU-only.  The next pass it reruns the training on the same input, but use's the M4's GPU.  At the tail end of the notebook, the following graph is plotted. 
![image](https://github.com/user-attachments/assets/b33ccf2c-4062-4072-97c6-380043f8b81a)
This CPU was 1739.810 seconds, the GPU was 188.117 seconds, about 10X improvement in training time with the M4 GPU.

# Conclusion
I bought a [Mac Mini M4](https://www.apple.com/shop/buy-mac/mac-mini/m4) for AI work.  I have been doing AI work w/Pytorch on my Dell Intel CPU.  I am looking for somethings significantly faster, but I am reluctant to buy a big NVIDIA GPU, at least for now.

This Setup helps me verify that I have the basic understanding to setup and use my M4 for AI work. Once setup and stable, I plan to put it in my server rack.  I dont want to use this as a desktop replacement, thus the extra effort to get remote access working.  
# References
This was a clone from 
-[pytorch-apple-silicon](https://github.com/mrdbourke/pytorch-apple-silicon) by [mrdbourke](https://github.com/mrdbourke)
-[Setup Mac for Machine Learning with PyTorch in 11 minutes (works for all M1, M2)](https://www.youtube.com/watch?v=Zx2MHdRgAIc)



