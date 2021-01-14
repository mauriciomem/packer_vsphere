## Debian 10 packer image build

### Files

 * Build declaration: `debian10.json`
 * Build parameters: `variables.json`
 * Preseed file: `http/preseed.json`

### Run

Complete the connection parameters in variables.json and run 

```
  packer build -var-file variables.json centos7.json
```

To pass values as environment variables its recommended to replace the variables declaration in variables.json with the folliwing sintax: ``"variable": "{{env `ENVVAR NAME`}}".``

Then you can call the variables through another file, using the `-var` parameter or declaring the variables outside the script with the env variable `PKR_VAR_variable=bar`

#### Building image with `-var` parameter

```
  packer build -var-file variables-env.json -var 'vmname=deb10image' debian10.json
```

#### Debugging

```
  PACKER_LOG=1 packer build -var-file variables-env.json -var 'vmname=deb10image' debian10.json
```

### References

#### Docs

https://www.debian.org/releases/buster/amd64/apb.en.html
https://www.debian.org/releases/buster/example-preseed.txt
https://wiki.debian.org/Keyboard

#### Troubleshooting

https://unix.stackexchange.com/questions/409212/preseed-directive-to-skip-another-cd-dvd-scanning
