## Centos 7 packer image build

### Files

 * Build declaration: `centos7.json`
 * Build parameters: `variables.json`
 * Kickstart file: `http/ks-minimal.json`

### Run

Complete the connection parameters in variables.json and run 

  packer build -var-file variables.json centos7.json

To pass values as environment variables its recommended to replace the variables declaration in variables.json with the folliwing sintax: ``"variable": "{{env `ENVVAR NAME`}}".``

Then you can call the variables through another file, using the `-var` parameter or declaring the variables outside the script with the env variable `PKR_VAR_variable=bar`

#### Building image with `-var` parameter

```
  packer build -var-file variables-env.json -var 'vmname=centos7image' centos7.json
```

#### Debugging

```
  PACKER_LOG=1 packer build -var-file variables-env.json -var 'vmname=centos7image' centos7.json
```
### References

#### Docs
https://docs.centos.org/en-US/centos/install-guide/Kickstart2/
https://docs.centos.org/en-US/8-docs/advanced-install/assembly_kickstart-commands-and-options-reference/
https://www.packer.io/docs/builders/vmware/vsphere-iso

#### Troubleshooting
https://github.com/jetbrains-infra/packer-builder-vsphere/issues/85
