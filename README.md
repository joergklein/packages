# Packages Repository

The rpm files are made for CentOS 8. I made this packages for my own use. Feel
free to use it, without any warranty. A list of all rpm files can you find
[Packages][1] list.

[1]: PACKAGES.md

An RPM is delivered in a single file, normally with a filename in the format:

```sh
<name>-<version>-<release>.src.rpm for source packages
<name>-<version>-<release>.<architecture>.rpm for binaries
```

## How to install a RPM file

### Download RPM Installation File

Typically, a web browser is used to locate and download a .rpm file. However, if
a browser is not available you can still download a file if you know where it’s
located. You may need to install a software tool called `wget` or `curl`.

```sh
curl -LJO http://some_website/sample_file.rpm
wget http://some_website/sample_file.rpm
```

### Install a RPM File

Install a .rpm package in CentOS:

```sh
sudo rpm –i sample_file.rpm
```

The `–i` switch tells the package manager you want to install the file. More
information on the RPM installer can be found in the RPM documentation `man
rpm`.

### Install RPM File with yum or dnf

Alternately, you can use the yum or dnf package manager to install .rpm files.

```sh
sudo dnf localinstall sample_file.rpm
```

The `localinstall` option instructions yum to look at your current working
directory for the installation file.

### Check RPM Dependencies
So far, this guide assumes the software either doesn’t have dependencies or
already has them installed.

To check the `.rpm` file for dependencies using the following command:

```sh
sudo rpm –qpR sample_file.rpm
```

The system should list all the dependencies:

`-q` This option tells RPM to query the file  
`–p` This option lets you specify the target package to query  
`–R` This lists the requirements for the package

### Remove RPM Package
The RPM installer can be used to remove (or uninstall) a software package.

```sh
sudo rpm –e sample_file.rpm
```

The `–e` option instructs RPM to `erase` the software.

