MAIN_PATH = File.dirname(__FILE__)

def colorize(text, color)
  color_codes = {
    :black    => 30,
    :red      => 31,
    :green    => 32,
    :yellow   => 33,
    :blue     => 34,
    :magenta  => 35,
    :cyan     => 36,
    :white    => 37
  }
  code = color_codes[color]
  if code == nil
    text
  else
    "\033[#{code}m#{text}\033[0m"
  end
end

def compile_markdown
  puts colorize("Compyling markdown", :blue)
  sh "jekyll build --safe"
end

desc "Prepare enviroment"
task :prepare_env do
  puts colorize("Installing dependencies", :blue)
  sh "gem install jekyll"
  sh "gem install redcarpet"
  sh "sudo easy_install Pygments"
end

desc "Compile"
task :compile do
  compile_markdown()
end

desc "Show test"
task :test => [:compile] do
  sh "open _site/index.html"
end

task :default => [:compile]
