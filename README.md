centos6_limit_break
===================

centos6 リミット解除集


接続処理が多い時の設定
======================

同時読み込みファイル数、同時接続数  
/etc/security/limits.conf

    * soft nofile 60000
    * hard nofile 60000

接続ポート範囲  
/etc/sysctl.cnf

    net.ipv4.ip_local_port_range = 1024 60000

切断時のタイムアウト時間  
/etc/sysctl.cnf

    net.ipv4.tcp_fin_timeout = 5

新規コネクションにTIME_WAIT状態のソケットを再利用することを許可    
/etc/sysctl.cnf

    net.ipv4.tcp_tw_reuse = 1

プロセス数（スレッド数）が多い時の設定
======================================

プロセス数  
/etc/security/limits.d/90-nproc.conf

    * soft nproc 65535

natセッション数が多い時の設定
=============================

接続可能なセッション数  
/etc/sysctl.cnf

    net.nf_conntrack_max = 100000



