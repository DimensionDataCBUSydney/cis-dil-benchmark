require 'fileutils'

task default: [:build_release]

version = '0.1'
pkg_file = "didata-cis-#{version}.tar.gz"

task :build_release => [ :clean ]do
  File.delete pkg_file if File.exist? pkg_file

  FileUtils.mkdir_p 'cis'

  # Set up directory
  %w[README.md LICENSE inspec.yml].each do |file|
    FileUtils.cp file, 'build'
  end
  %w[libraries controls].each do |file|
    FileUtils.cp_r file, 'cis/'
  end


  system "gtar -cvz --owner=0 --group=0  -f #{pkg_file} controls libraries inspec.yml README.md LICENSE"

end

task :clean do
  FileUtils.rm_rf 'cis', secure: true
end