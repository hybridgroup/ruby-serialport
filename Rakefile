require 'rubygems'
require 'rake'

gem 'rake-compiler', '>= 0.4.1'
require "rake/extensiontask"

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gemspec|
    gemspec.name = "hybridgroup-serialport"
    gemspec.summary = "Library for using RS-232 serial ports."
    gemspec.description = "Ruby/SerialPort is a Ruby library that provides a class for using RS-232 serial ports."
    gemspec.email = "serialport@hybridgroup.com"
    gemspec.homepage = 'http://github.com/hybridgroup/ruby-serialport/'
    gemspec.authors = ['Guillaume Pierronnet', 'Alan Stern', 'Daniel E. Shipton', 'Tobin Richard', 'Hector Parra', 'Ryan C. Payne']
    gemspec.has_rdoc = true
    gemspec.extensions << 'ext/native/extconf.rb'
    gemspec.version = "1.2.0"
    gemspec.files = [
      "CHANGELOG",
      "CHECKLIST",
      "LICENSE",
      "MANIFEST",
      "README",
      "Rakefile",
      "VERSION",
      "ext/native/extconf.rb",
      "ext/native/posix_serialport_impl.c",
      "ext/native/serialport.c",
      "ext/native/serialport.h",
      "ext/native/win_serialport_impl.c",
      "lib/serialport.rb",
      "hybridgroup-serialport.gemspec",
      "test/miniterm.rb",
      "test/set_readtimeout.rb"
    ]

    Rake::ExtensionTask.new "serialport", gemspec do |ext|
      #ext.lib_dir = File.join(*['lib', ENV['FAT_DIR']].compact)
      ext.ext_dir = "ext/native"
    end
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler not available. Install it with: sudo gem install jeweler -s http://gemcutter.org"
end

task :clean do
  rm_rf(Dir['doc'], :verbose => true)
  rm_rf(Dir['pkg'], :verbose => true)
end

