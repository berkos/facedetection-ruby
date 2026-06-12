# frozen_string_literal: true

require "bundler/gem_tasks"

task gem: :build

begin
  require "rb_sys/extensiontask"

  GEMSPEC = Gem::Specification.load("libfacedetection.gemspec")

  RbSys::ExtensionTask.new("libfacedetection-ruby", GEMSPEC) do |ext|
    ext.lib_dir = "lib/libfacedetection"
  end
rescue LoadError
  warn "rb_sys not available, skipping compile tasks (run `bundle install` to enable them)"
end
