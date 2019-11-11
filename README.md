# wifi_location_switcher

WiFiのSSID名に合わせて、ネットワーク環境(location)も一緒に変更するシェルです。 

※ WiFiのSSID名と同じ名前で「ネットワーク環境」を作成してください  
※ デフォルトで用意されている「自動」(Automatic) 名称は残しておいてください  
※ WiFiを切った場合、動作しないようにしています。

### example
    SSID: example-wifi
    ネットワーク環境名: example-wifi
    
    上記のように、名称の完全一致で切り替わります。
    ネットワーク環境に、同じ名前が存在しない場合は「自動(Automatic)」を選択します。

### setup
    ### 本体をcloneしてディレクトリ移動
    % git clone git@github.com:chanshige/wifi_location_switcher.git
    % cd wifi_location_switcher
    
    ### 各ファイルを所定の位置にコピー
    % sudo cp wifi_location_switcher /usr/local/etc/
    % sudo cp chanshige.wifi.location.switcher.plist ~/Library/LaunchAgents/

    ### 実行権限
    % sudo chmod a+x /usr/local/etc/wifi_location_switcher
    
    ### launchctl に登録
    % cd ~/Library/LaunchAgents
    % sudo launchctl load chanshige.wifi.location.switcher.plist

    ### 登録確認
    % sudo launchctl list |grep chanshige.wifi.location.switcher
    
    ### OSシステム再起動 restart ###

### remove (使用をやめる)
    % cd ~/Library/LaunchAgents
    % sudo launchctl unload chanshige.wifi.location.switcher.plist
    % sudo launchctl remove chanshige.wifi.location.switcher.plist
    % sudo rm -r chanshige.wifi.location.switcher.plist
    
    ### 削除確認
    % sudo launchctl list |grep chanshige.wifi.location.switcher
    
    ### シェル本体を削除
    % sudo rm -r /usr/local/etc/wifi_location_switcher
