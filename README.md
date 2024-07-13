# HelloWorld Activity Flatpak

This is an example Sugar Desktop Activity, that follows the "Hello World" tradition of being a small and simple demonstration of a complete program for a system.

## How To Build

```
git clone https://github.com/tchx84/org.sugarlabs.HelloWorld.git
cd org.sugarlabs.HelloWorld
flatpak -y --user install flathub org.gnome.{Platform,Sdk}//46
flatpak -y --user install org.sugarlabs.BaseApp//24.04
flatpak-builder --user --force-clean --install build org.sugarlabs.HelloWorld.json
```

## Check For Updates

Install the flatpak external data checker
```
flatpak --user install org.flathub.flatpak-external-data-checker
```

Now to update every single module to the latest stable version use
```
cd org.sugarlabs.HelloWorld
flatpak run --filesystem=$PWD org.flathub.flatpak-external-data-checker org.sugarlabs.HelloWorld.json
```
