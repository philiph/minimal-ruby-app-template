LIB_FOLDER = File.expand_path("./lib", __dir__)
$LOAD_PATH.unshift LIB_FOLDER

def lib_files_to_require
  Dir.glob(File.join(LIB_FOLDER, "**", "*.rb"))
     .map { |path| path.delete_prefix("#{LIB_FOLDER}/") }
     .map { |path| path.delete_suffix(".rb") }
end

desc "Opens an IRB console to interact with the code"
task :console do
  require "irb"
  require "irb/completion"

  lib_files_to_require.each do |filename|
    puts "Requiring file: #{filename}"
    require filename
  end

  ARGV.clear
  IRB.start
end
