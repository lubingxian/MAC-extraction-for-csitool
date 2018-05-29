# MAC-extraction-for-csitool
A MAC address extraction plugin for the [Linux 802.11n CSI Tool](https://github.com/dhalperi/linux-80211n-csitool).

# Usage
To use this code, you will need all the files from https://github.com/dhalperi/linux-80211n-csitool-supplementary.

1. To log both CSI measurements and packet payloads (MAC address)：
~~~
sudo modprobe -r iwlwifi mac80211
sudo modprobe iwlwifi connector_log=0x5
~~~

2. In matlab:
~~~
csi_trace = read_bf_file('csi-data');
csi_entry = csi_trace{1}

csi_entry =
    timestamp_low: 276797143
       bfee_count: 269
              Nrx: 3
              Ntx: 1
           rssi_a: 37
           rssi_b: 38
           rssi_c: 35
            noise: -92
              agc: 45
             perm: [2 1 3]
             rate: 10502
              csi: [1×3×30 double]
          MAC_Src: '4C:5E:0C:11:FB:F9'
          MAC_Des: '00:21:6A:95:1A:50'
~~~

# Reference
* http://dhalperi.github.io/linux-80211n-csitool/faq.html
* https://github.com/dhalperi/linux-80211n-csitool-supplementary/issues/101

# Contact
[Bingxian Lu](https://lubingxian.cn)   
Email: bingxian.lu@gmail.com

To cite this work, the best reference is our paper published in IEEE SECON 2016:

Bingxian Lu, Zhicheng Zeng, Lei Wang, Brian Peck, Daji Qiao, and Michael Segal. 
Confining Wi-Fi Coverage: A Crowdsourced Method Using Physical Layer Information. 
IEEE SECON, 2016.
