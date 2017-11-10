2.获取源代码

git branch -a
git checkout lede-17.01

svn co svn://svn.openwrt.org/openwrt/trunk/
git clone -b lede-17.01 https://git.lede-project.org/source.git lede-17.01
git clone https://git.lede-project.org/source.git lede-x86
git clone https://github.com/openwrt-mirror/openwrt.git mw4530rt
#svn co svn://svn.openwrt.org/openwrt/branches/barrier_breaker -r42625
svn update
#cp feeds.conf.default feeds.

./scripts/feeds update -a
./scripts/feeds install -a

ln -s ~/lede/dl/
ln -s ~/lede/files-x86/ files
ln -s ~/lede/files-mw4530r/ files
ln -s ~/lede/my_packages/ ./package

make V=99 FORCE_UNSAFE_CONFIGURE=1

