mkdir /etc/aceproxy
cp ../etc/* /etc/aceproxy/
docker run -d --restart always --name aceproxy -p 8000:8000 -p 8081:8081 -v /etc/aceproxy/torrenttv.py:/aceproxy/plugins/config/torrenttv.py -v /etc/aceproxy/p2pproxy.py:/aceproxy/plugins/config/p2pproxy.py --link acestream:acehost --link vlc-nox:vlchost odayny/aceproxy
