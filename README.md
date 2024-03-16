# Pukllanapac Activity Flatpak

Pukllanapac is a sliding-puzzle game, the objective is to rearrange tiles so that all of the circles (and semicircles) are composed of sectors of the same color.

To know more refer https://github.com/sugarlabs/pukllanapac

## How To Build

```
git clone https://github.com/flathub/org.sugarlabs.Pukllanapac.git
cd org.sugarlabs.Pukllanapac
flatpak --user remote-add --if-not-exists flathub-beta https://flathub.org/beta-repo/flathub-beta.flatpakrepo
flatpak -y --user install flathub-beta org.gnome.{Platform,Sdk}//46beta
flatpak -y --user install org.sugarlabs.BaseApp//24.04
flatpak-builder --user --force-clean --install build org.sugarlabs.Pukllanapac.json
```

## Check For Updates

Install the flatpak external data checker
```
flatpak --user install org.flathub.flatpak-external-data-checker
```

Now to update every single module to the latest stable version use
```
cd org.sugarlabs.Pukllanapac
flatpak run --filesystem=$PWD org.flathub.flatpak-external-data-checker org.sugarlabs.Pukllanapac.json
```