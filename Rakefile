require 'fileutils'

task default: [:build_release]

version = '0.1'
pkg_file = "didata-cis-#{version}.tar.gz"

task :build_release do
  File.delete pkg_file if File.exist? pkg_file


  system "gtar -cvz --owner=0 --group=0  -f #{pkg_file} controls libraries inspec.yml README.md LICENSE"

end

