# YouCompleteMe installation
this file describe the process to install YouCompleteMe plugin of Vim on Ubuntu14.04.

## Preflight
### Install clang
1. System install clang to compile YouCompleteme
<pre><code>sudo apt-get install clang</code></pre>
2. download clang-4.0
the distribution name of clang-4.0 is:<pre><code>clang+llvm-4.0.0-x86_64-linux-gnu-ubuntu-14.04.tar.xz</code></pre>
clang-4.0 will be downloaded when you execute command <b>./install.py</b>
<p>Hence, you can use download software to download this file.  Then copy this file to path:<b>/home/zhangjiayuan/.vim/bundle/YouCompleteMe/third_party/ycmd/clang_archives/</b></p>

### vim installation and problems
<p>if you use command as follows:  </p>
<pre><code>sudo apt-get install vim</code></pre>
<p>Maybe you will face the problems: </p>
<pre><code>YouCompleteMe unavailable: requires Vim compiled with Python (2.6+ or 3.3+) support</code></pre>
<p>To deal with this problem, you should download vim and compile it.  As follows:</p>
<pre>
	<code>
git clone git@github.com:vim/vim.git
./configure --with-features=huge --enable-pythoninterp --enable-rubyinterp --enable-luainterp --enable-perlinterp --with-python-config-dir=/usr/lib/python2.7/config-x86_64-linux-gnu/ --enable-gui=gtk2 --enable-cscope --prefix=/usr
cd vim && make && sudo make install
	</code>
</pre>
	
### YouComplemeMe installation
<pre><code>cd ~/.vim/bundle/YouCompleteMe/
CC="/usr/bin/clang" CXX="/usr/bin/clang++" ./install.py --clang-completer</code></pre>

