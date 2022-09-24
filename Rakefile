task :host do
  sh "budo -d docs"
end

task :download do
  sh <<-EOS
curl -L -o docs/maplibre-gl.js \
https://unpkg.com/maplibre-gl@latest/dist/maplibre-gl.js
curl -L -o docs/maplibre-gl.js.map \
https://unpkg.com/maplibre-gl@latest/dist/maplibre-gl.js.map
curl -L -o docs/maplibre-gl.css \
https://unpkg.com/maplibre-gl@latest/dist/maplibre-gl.css
  EOS
end

task :head do
  sh <<-EOS
charites build head.yml docs/head.json
  EOS
end

task :intl do
  sh <<-EOS
charites --provider maplibre build maplibre-intl.yml \
docs/maplibre-intl.json
  EOS
end

task :tilejson do
  sh <<-EOS
cat tile.yml | \
ruby -rjson -ryaml -e 'print YAML.load(STDIN.read).to_json' | \
jq . > docs/tile.json
  EOS
end

task :serve do
  sh "charites serve maplibre-intl.yml"
end
