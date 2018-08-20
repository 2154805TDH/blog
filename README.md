# Cent OS 初始化

更新系统：\
`yum update -y`

安装 EPEL 仓库：\
`yum install -y epel-release`

安装开发工具：\
`yum groupinstall -y "Development Tools"`\
`yum install -y ncurses-devel zlib-devel texinfo gtk+-devel gtk2-devel qt-devel tcl-devel tk-devel libX11-devel kernel-headers kernel-devel`
