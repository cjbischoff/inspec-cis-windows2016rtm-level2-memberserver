# inspec-cis-windows2016rtm-level2-memberserver

## This compliance profile utilizes tests based upon [CIS Benchmark for Microsoft Windows Server 2016 RTM](https://www.cisecurity.org/benchmark/microsoft_windows_server/)

### Standalone Usage

This Compliance Profile requires [InSpec](https://github.com/chef/inspec) for execution:

#### Local Usage

```
$ git clone git@github.com:cjbischoff/inspec-cis-windows2016rtm-level2-memberserver.git
$ inspec exec inspec-cis-windows2016rtm-level1-memberserver
```

#### Remote Usage against a system

```
$ inspec exec https://github.com/cjbischoff/inspec-cis-windows2016rtm-level2-memberserver -t winrm://Administrator@windowshost --password 'your-password'
```

#### Test Kitchen Usage

Within `inspec.yml` file add a depends:

```
depends:
    - name: inspec-cis-windows2016rtm-level2-memberserver
      git:  https://github.com/cjbischoff/inspec-cis-windows2016rtm-level2-memberserver
```

Within the `controls` directory add a place folder to include the profile and any excluisions from the standard that are not relevant

create the control file `cis_windows2016rtm_level2_memberserver.rb` with the following contents:
```
include_controls 'windows-cis_windows2016rtm_level2_memberserver'
```

Within that control file you can also dynamicing modify specfics of the control and explicily include/excdie controls via [profile inheritance](https://blog.chef.io/2017/07/06/understanding-inspec-profile-inheritance/)
