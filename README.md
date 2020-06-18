# GDAL flatpak

flatpak for GDAL.

## Usage

    flatpak run org.osgeo.gdal --formats 
    flatpak run --command=ogrinfo org.osgeo.gdal --version


## Build


    sudo apt-get install flatpak-builder elfutils 

    flatpak install flathub org.freedesktop.Sdk/x86_64/19.08 
    flatpak install flathub org.freedesktop.Platform/x86_64/19.08 

    flatpak-builder build --force-clean org.osgeo.gdal.json 
    # Test
    flatpak-builder --run build org.osgeo.gdal.json ogr2ogr --formats 
    # Put the app in a repository
    flatpak-builder --repo=repo build --force-clean org.osgeo.gdal.json 
    # Install
    flatpak --user remote-add --no-gpg-verify local-repo repo  
    flatpak --user install local-repo org.osgeo.gdal  
