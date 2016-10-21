#run rake zip or bundle exec rake zip from directory

require 'rubygems'
require 'bundler'
require 'fileutils'
require 'zip'
Bundler.require(:default)

task :zip do 
  theme = File.join(File.dirname(__FILE__), 'theme.zip')

Zip.setup do |c|
  c.on_exists_proc = true
  c.continue_on_exists_proc = true
end

  Zip::File.open(theme, Zip::File::CREATE) do |zipfile|
    Dir.glob("**/*.{html,css,png,gif,jpg,eot,svg,ttf,woff,js}").each do |path|
      zipfile.add(path, File.join(File.dirname(__FILE__), path))
    end
  end
end