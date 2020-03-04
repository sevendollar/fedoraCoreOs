# https://docs.fedoraproject.org/en-US/fedora-coreos/bare-metal/
1. Writing the FCC file(yaml format):

2. transpile the FCC file to ignition file, Using FCCT(Fedora CoreOS Config Transpiler):
  docker run -i --rm quay.io/coreos/fcct:latest --pretty --strict < example.fcc > example.ign

3. Installing from ISO:
  - load the FCOS ISO image on the bare metal machine.
    https://getfedora.org/coreos/download/
  
  - (optional)use python http module to share ignition config file from your working machine:
    python3 -m http.server
  
  - fetch your Ignition config:
    curl -LO http://example.com/example.ign
  
  - run coreos-installer:
    sudo coreos-installer install /dev/sda --ignition example.ign
  
  - power off the machine:
    poweroff
  
  - remove the CD-ROM media(ISO image):

  - boot the machine


