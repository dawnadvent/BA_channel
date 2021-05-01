# WINRDP BA_channel

build yml :https://pastebin.com/MBVNQp2G

Remotedesktop chrome : https://remotedesktop.google.com/headless

tutorial yt Bang Android
Watch Video: https://youtu.be/HXCjo8Ky3RA

# Selamat Mencoba Dan Semoga Berkah Teman Teman


name: Windows-CRD
 
on: 
  workflow_dispatch:
    inputs:
      authcode:
        description: 'Enter CRD code'
        required: true
      pincode:
        description: 'Six digit Pin'
        required: true
 
jobs:
  build:
    runs-on: windows-latest
 
    steps:
    - uses: actions/checkout@v2
    - name: Initializing Setup
      run: ./setup.ps1
    - name: Starting CRD
      run: ${{ github.event.inputs.authcode }} -pin=${{ github.event.inputs.pincode }}
    - name: Keep Alive
      run: ./timeout.ps1
