Vagrant.configure("2") do |config|

    # マシン構成
    config.vm.box = "koalephant/debian12-amd64"

    # ホスト名
    config.vm.hostname = "rails-01"

    # ストレージ設定
    config.vm.synced_folder "src/", "/var/www/app", create:"true"

    # ネットワーク設定

    # HttpとSSHのポートフォワーディング設定
    config.vm.network :forwarded_port, guest: 80, host: 8800, id: "http"
    config.vm.network :forwarded_port, guest: 22, host: 5000, id: "ssh"
    config.vm.network :private_network, ip: "192.168.1.10"

    #プロバイダー設定
    config.vm.provider "virtualbox" do |vb|
        # GUIを使用しない
        vb.gui = false

        # 仮想マシンの名前
        vb.name = "Debian12(Rails)"

        # 仮想マシンのCPUコア数
        vb.cpus = 2

        # 仮想マシンのメモリ容量
        vb.memory = "2048"

        # タイムアウトの時間の伸ばす
        config.vm.boot_timeout = 8000
    end
end