## How to install old version of R

I had MacOS High sierra (10.12.x) with R version 4.0.x installed. I needed to install a package but it was not available for R-4.0.x. I thought about downgrading R version to 3.6.3. I install all softwares in Mac with [brew](brew.sh) package manager. Basically, the command 
```
brew install packagename
```
installs the latest version of the package or R in this case. I cannot specify R version to install. 

However, brew now allows to extract the formula for a particular version of the package and use that formula to install the particular version of R.

To get formula for R-3.6.3, use
```
brew extract --version=3.6.3 R brewsci/science
```
Here, brewsci/science is the tap. If you have not tapped brewsci/science, use brew tap brewsci/science to tap it.

brew extract command will get a file for R-3.6.3 and save it. I got saved at 
```
/usr/local/Homebrew/Library/Taps/brewsci/homebrew-science/Formula/r@3.6.3.rb
```

The I installed with the command:
```
brew install /usr/local/Homebrew/Library/Taps/brewsci/homebrew-science/Formula/r@3.6.3.rb
```

I got an error because the link to gss file https://cloud.r-project.org/src/contrib/gss_2.1-12.tar.gz didn't exist any more as the gss version was updated. The new link was https://cloud.r-project.org/src/contrib/gss_2.2-2.tar.gz. So i edit the file and updated the link and the sha256 for the file as well. After this the installation worked. 
