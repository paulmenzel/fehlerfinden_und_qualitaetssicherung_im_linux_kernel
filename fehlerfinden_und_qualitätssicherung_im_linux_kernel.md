% Fehlerfinden und Qualitätssicherung im Linux-Kernel
% Paul Menzel (Max-Planck-Institut für molekulare Genetik)
% 10. März 2018

## Wer bin ich?

![Logo of Max Planck Institute for Molecular Genetics](images/MPIMG_helix_rgb.png){ height=25% }\


- Systemarchitekt beim [Max-Planck-Institut für molekulare Genetik](https://www.molgen.mpg.de/)
- Diplom-Wirtschaftsmathematiker ([TU Berlin](https://www.tu-berlin.de/))
- FLOSS-Befürworter

## Präsentation

Folien in Markdown mit [Pandoc](https://pandoc.org/) nach LaTeX-Beamer umgewandelt, verfügbar auf GitHub.

<https://github.com/paulmenzel/fehlerfinden_und_qualitätssicherung_im_linux_kernel>

## Problem

-   Hersteller/OEMs entwickeln nur für Microsoft Windows.
-   Wenige Ausnahmen: Google Chromebooks und Apple
-   Anderen Anbieter passen nur an

-   Mehr Motivation: Vortrag [*Hilf mit, damit Linux nur besser und nie schlechter wird* von Thorsten Leemhuis, Sonntag 10 Uhr](https://chemnitzer.linux-tage.de/2018/programm/beitrag/253)
-   Hohe Änderungsraten und Testlabore erst im Kommen

## Arbeit mit Entwicklern

-   Linux-Kernel in Distributionen meist nicht aktuell
-   Linux-Kernel-Entwicklern bevorzugen Meldungen bezüglich der aktuellen Version
    -   Zweig *master* in Linus’ Git-Depot
    -   Entsprechender Entwicklungszweig

# Neuer Linux-Kernel

## Pakete

-   Ubuntu: http://kernel.ubuntu.com/~kernel-ppa/mainline/
-   Fedora: https://fedoraproject.org/wiki/Kernel_Vanilla_Repositories
-   Debian: manchmal in *experimental*: https://packages.debian.org/linux-image-4.16
-   andere Distributionen ähnlich

## Selber bauen (Debian)

```
$ git clone https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git
$ cd linux
$ cp -a /boot/config-4.15.0-1-amd64 .config
$ make help
$ make olddefconfig
$ make localmodconfig
$ make bindeb-pkg -j`nproc`
$ sudo dpkg -i ../linux*.deb
```

# Ausblick

## kselftest

-   Mehr Tests

## Fazit

1.  Jeder kann mitmachen.

# Fragen
