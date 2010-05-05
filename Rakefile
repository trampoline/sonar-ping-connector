require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "sonar_ping_connector"
    gem.summary = %Q{A handy ping connector for the Trampoline SONAR connector framework.}
    gem.description = %Q{This connector repeatedly pings a remote host and alerts a sysadmin when the host is unreachable.}
    gem.email = "hello@empire42.com"
    gem.homepage = "http://github.com/trampoline/sonar-ping-connector"
    gem.authors = ["Peter MacRobert", "Mark Meyer"]
    
    gem.add_dependency "sonar_connector", ">= 0.5.6"
    gem.add_dependency "net-ping", ">= 1.3.2"
    
    gem.add_development_dependency "rspec", ">= 1.2.9"
    gem.add_development_dependency "rr", ">= 0.10.5"
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

require 'spec/rake/spectask'
Spec::Rake::SpecTask.new(:spec) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.spec_files = FileList['spec/**/*_spec.rb']
end

Spec::Rake::SpecTask.new(:rcov) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.pattern = 'spec/**/*_spec.rb'
  spec.rcov = true
end

task :default => :spec
task :spec => :check_dependencies
