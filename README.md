# This image has been replaced, please migrate to the new one!!!
All images now live under the same repo https://github.com/CeruleanDerpo/kinoite-nvidia
Please rebase to the new `kinoite-nvidia-niri` image by following these steps:
- First rebase to the unsigned image, to get the proper signing keys and policies installed:
  ```
  bootc switch ghcr.io/ceruleanderpo/kinoite-nvidia-niri:latest
  ```
- Reboot to complete the rebase:
  ```
  systemctl reboot
  ```
- Then rebase to the signed image, like so:
  ```
  bootc switch --enforce-container-sigpolicy ghcr.io/ceruleanderpo/kinoite-nvidia-niri:latest
  ```
- Reboot again to complete the installation
  ```
  systemctl reboot
  ```

The `latest` tag will automatically point to the latest build. That build will still always use the Fedora version specified in `recipe.yml`, so you won't get accidentally updated to the next major version.
