# https://github.com/afriggeri/CV
# http://www.LaTeXTemplates.com

@name = 'Frank Luan'
@src = '_source'

desc 'Render using XeLaTex, specify version by appending V='
task :default do
  file = render(ENV['V'] || 'screen')
  `open "#{file}"`
end

desc 'Deploy the latest screen version onto server'
task :deploy do
  file = render
  puts 'Uploading to server'
  `scp "#{render}" me:~/www/franklsf.org/Resume.pdf`
end

desc 'Cleans up temporary files'
task :clean do
  puts 'Cleaning up...'
  `rm _a.*`
end

def render(ver='screen')
  filename = "#{@name} (#{ver}).pdf"
  puts "Rendering #{filename}"
  system "cat versions/#{ver}.tex #{@src}.tex > _a.tex"
  puts 'Source generated. Rendering...'
  system 'latexmk -xelatex _a.tex'
  `mv _a.pdf "#{filename}"`
  filename
end
