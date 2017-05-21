# common-ubuntu-app-issues

1. Error installing packages in RStudio
   Solution:
   
   We have isolated this to something in /usr/local/lib/R/site-library, and it is not R3.2 or RStudio's fault. The error disappears if you edit /etc/R/Renviron to not set R_LIBS_SITE by commenting out

#R_LIBS_SITE=${R_LIBS_SITE-'/usr/local/lib/R/site-library:/usr/lib/R/site-library:/usr/lib/R/library'}

And then launching

$ R_LIBS_SITE=/usr/lib/R/site-libray:/usr/lib/R/library rstudio
