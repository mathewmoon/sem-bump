#sem-bump

CLI tool for bumping semantic version strings

##Usage

```
usage: sem-bump [-h] [-v VERSION] [-f VERSION_FILE] [-i INCREMENT] {major,minor,patch}

positional arguments:
  {major,minor,patch}   Component of the version to bump

optional arguments:
  -h, --help            show this help message and exit
  -v VERSION, --version VERSION
                        Version string to bump
  -f VERSION_FILE, --version-file VERSION_FILE
                        Read from and/or write to --version-file
  -i INCREMENT, --increment INCREMENT
                        The amount to increment by
```

Will also read the version string (-v) from stdin.

##Examples
```
> echo 0.0.1 | sem-bump major -i 1  # Read from stdin and bump to next major version
1.0.0
> sem-bump major -i 1 -v 0.1.0  # Take version string as an arg and bump to next major version
1.0.0
> echo "2.3.4" >version.txt  # Create a version.txt file and update it 25 patch releases
> sem-bump patch -f version.txt -i 25
> cat version.txt
2.3.29
```
