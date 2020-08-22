desc "Load and reload current dir ruby files in irb."

task :console do
  require 'irb'

  # Dir['./**/*.rb'].sort.each { |file| require file } # this works as well

  @rbfiles = File.join("**", "*.rb")

  Dir.glob(@rbfiles, base: ".") { |file| require_relative file }

  def reload!
    Dir.glob(@rbfiles, base: ".") { |file| load file }
    "Environment reloaded."
  end

  ARGV.clear

  IRB.start
end
