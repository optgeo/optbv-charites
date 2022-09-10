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

