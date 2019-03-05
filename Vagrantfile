## Example shim, the contents of this should replace the traditional 'Vagrantfile'
# Small shim to pull down a remote vagrantfile
require 'open-uri'
require 'openssl'
require 'date'

# Define variables
remote_vagrantfile = "https://raw.githubusercontent.com/boxrick/ansible-remote-vagrantfile/master/vagrantfile_ansible_roles"
downloaded_vagrantfile = '.vagrant/downloaded.vagrantfile'
cached_vagrantfile_hours = 6

# Define functions
def download_remote(remote, local, msg)
  puts "#{msg}, Downloading remote Vagrantfile to #{local}"
  download = open(remote)
  IO.copy_stream(download, local)
end

# Download file if not already present or cache time has expired
if not File.file?(downloaded_vagrantfile)
    download_remote(remote_vagrantfile, downloaded_vagrantfile, 'File missing')
elsif ((Time.now - File.stat(downloaded_vagrantfile).mtime).to_i / 3600) > cached_vagrantfile_hours
    download_remote(remote_vagrantfile, downloaded_vagrantfile, 'File older than 6 hours')
end

# Load file in and run
eval File.read(downloaded_vagrantfile)
