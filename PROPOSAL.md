# Secure Desktop Spin

Fedora Desktop spin for paranoid people. This Pad serves for gathering ideas/brainstorming. If you have an idea (even from the "almost sci-fi" category) write it down please.

## What are the assumptions about users of the spin

 * The knowledge of IT of the user is above average. He knows:
  * what TCP/IP is
  * what a firewall is and what is serves for
  * about symmetric and asymmetric cryptography, PKI
 * The user doesn't expect that things on the system will happen automagically all the time and doesn't mind being asked for decisions on security related actions

## Use cases (i.e. what should be expected to work even after a brutal lockdown)

 * Web browsing (well, this is a special case of the item bellow this one...)
 * Various network clients - ssh, ftp, ntp?, vpn?
 * Devel/messy work in virtual machines? containers/vagrant?
 * Multimedia processing? -- photos, videos from personal devices
 * Office (writing documents, viewing, graphics...)
 
## Random Ideas

### Monitoring

* Something should analyze logs for weird things and warnings. User should be notified about anything suspicious but not spammed by every failed ssh login (probably should learn what to show and when? Bayes FTW?

* Run OpenSCAP scans? Probably shuld SCE rather than OVAL for creating non-retarded tests...

### System Security

* Apps should run in confined environment, sandboxed when possible
  * PDF viewing automatically sandboxed (with possibility to run non sandboxed?)
  * images viewing automatically sandboxed?

### Network Security

 * Firewall(d) is installed and configured by default? if using firewalld, provide own zones with better names, definitions and documentation (and maybe try to merge this upstream after they evolve to a good state)
   * we could also use firehol for high-level firewall policy definition, it's better -- intuitive syntax (IMHO)

 * NetworkManager
   * don't do things automagically, even dhcp configuration -- should prevent hijaking traffic by rogue devices (USB network cards)

 * WiFi: look for targeted attacks (deauth, impersonation)? I have SW for this but it's not published yet...

 * WiFi: randomized HW address, no sending of known SSIDs

#### Web Security

 * What's better? Firefox vs. Chrome? I don't use Chrome so I don't know.
 * Firefox has a lot of nice security extensions:
   * certificate patrol
   * NoScript
   * uBlock (AdBlock)
   * RequestPolicy
   * https everywhere
 * NO FLASH PLUGIN (disable the whole plugin system somehow? make it harder to accidentally, covertly install plugins?)

### Device Security

 * USBGuard is installed with some sane policy
   * allow 1 USB keyboard, 1 USB mouse
   * allow real USB flash disks (without additonal interfaces)
   * yubikeys only with exported serial number?

 * Think about how to prevent loading of kernel modules without user review (after entering multi user mode only)?
   * the idea is to limit the set of kernel modules that can be loaded without the user's review

### Crypto

 * Disk encryption enabled by default
 * No preinstalled CA certificates? Or not enabled by default and enable case-by-case? How?
 
### SELinux

 * turned ON by default
 * Confine the user
 * Remove unconfied_t
 * Make sure it's not that easy to disable SELinux? (i.e. remove setenforce etc, LOL) But make it possible for debugging (probably selinux=0 for kernel is good enough...)

