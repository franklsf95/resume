# https://github.com/afriggeri/CV
# http://www.LaTeXTemplates.com

name = 'Frank Luan'
src = '_source'

task :default do
  ver = ENV['V'] || 'screen'
  filename = "#{name} (#{ver})"
  puts "Rendering #{filename}.pdf"
  system "cat versions/#{ver}.tex #{src}.tex > _a.tex"
  puts 'Source generated. Rendering...'
  system 'latexmk -xelatex _a.tex'
  `mv _a.pdf "#{filename}.pdf"`
  `open "#{filename}.pdf"`
end

task :clean do
  puts 'Cleaning up...'
  `rm _a.*`
end
