This is an example of an encrypted mp4 that contains samples that are entirely clear in the same fragment as encrypted samples.

This can trip up browsers due to how they flag encrypted samples.

## Creation

Created from black-red mp4 via the following:

```
ffmpeg -f concat -i input.txt -framerate 60 black-red.mp4
```
then
```
packager-win.exe in=black-red.mp4,stream=video,output=clear-samples-widevine.mp4 --protection_scheme cenc --enable_widevine_encryption --key_server_url https://license.uat.widevine.com/cenc/getcontentkey/widevine_test --content_id 7465737420636f6e74656e74206964 --signer widevine_test --aes_signing_key 1ae8ccd0e7985cc0b6203a55855a1034afc252980e970ca90e5202689f947ab9 --aes_signing_iv d58ce954203b7c9a9a9d467f59839249 --mpd_output h264.mpd --hls_master_playlist_output h264_master.m3u8
```