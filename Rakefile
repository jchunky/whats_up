require "bundler/gem_tasks"
require "rspec/core/rake_task"
require "sdoc"

RSpec::Core::RakeTask.new("spec")

# Quick hack until SDoc gets fixed
class RDoc::Generator::SDoc; alias :basedir :base_dir; end

RDoc::Task.new do |rdoc|
  rdoc.rdoc_dir = "doc/rdoc"
  rdoc.title = "whats_up Documentation"

  rdoc.options << "-f" << "sdoc"         # format with SDoc
  rdoc.options << "-T" << "rails"        # use the Rails template
  rdoc.options << "-c" << "utf-8"
  rdoc.options << "-g"                   # link to GitHub
  rdoc.options << "-m" << "README.rdoc"  # use README.rdoc as main file
  rdoc.options << "-v"                   # verbose

  rdoc.rdoc_files.include "README.rdoc"
  rdoc.rdoc_files.include "lib/**/*.rb"
end
