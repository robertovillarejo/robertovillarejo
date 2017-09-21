---
layout: post
title:  "Instalación de StarUML en Ubuntu"
date:   2017-09-19 10:53:00 +0000
categories:
---

# Instalación de StarUML en Ubuntu

1. Descarga la dependencia libgcrypt11
`wget https://launchpad.net/ubuntu/+archive/primary/+files/libgcrypt11_1.5.3-2ubuntu4.2_amd64.deb`

2. Instala libgcrypt11
`dpkg -i libgcrypt11_1.5.3-2ubuntu4.2_amd64.deb`

3. Descarga StarUML x86 o x64 según sea el caso:
[Descargar StarUML](http://staruml.io/download)

4. Instala StarUML:
`dpkg -i StarUML-v2.8.0-64-bit.deb`
