# Zovan

## Camera

1. Install `go2rtc` binary to `/usr/local/bin`.
2. Create a new user `useradd -r -s /bin/false go2rtc`.
3. Create a new systemd service file `systemctl edit --full go2rtc.service` with the contents
   of the `./go2rtc/go2rtc.service` file.
4. Copy the `./go2rtc/go2rtc.yaml` file to `/etc/go2rtc.yaml`.
5. Start the service with `systemctl enable --now go2rtc`
6. In Fluidd, add a new camera with the following settings:
   - **Name:** Overview
   - **Stream Type:** WebRTC (go2rtc)
   - **Camera URL Stream:** `http://zovan.int.bksp.in:1984/ws?src=3d-camera-overview`
   - **Camera URL Snapshot:** `http://zovan.int.bksp.in:1984/api/frame.jpeg?src=3d-camera-overview`
