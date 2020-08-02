#Usage:
jobs:
  build:
    runs-on: macOS-latest
    steps:
    - name: 'Download Provisioning Profiles'
      id: provisioning
      uses: apple-actions/download-provisioning-profiles@v1
      with: 
        bundle-id: 'com.example.App'
        profile-type: 'IOS_APP_STORE'
        issuer-id: ${{ secrets.APPSTORE_ISSUER_ID }}
        api-key-id: ${{ secrets.APPSTORE_KEY_ID }}
        api-private-key: ${{ secrets.APPSTORE_PRIVATE_KEY }}
  
    - name: 'Another example step'
      run: echo ${{ steps.provisioning.outputs.profiles hakingaiphone
