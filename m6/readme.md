# Task 6.2#


**1.**  I created three virtual machines and configured network adapters for them.

![image](https://user-images.githubusercontent.com/42848618/147408004-24a33d39-dd8c-475c-8351-09d81c4e9daf.png)

![image](https://user-images.githubusercontent.com/42848618/147408012-2f9cb128-0316-41cb-9d67-fc241d6c9742.png)

![image](https://user-images.githubusercontent.com/42848618/147408016-07fa207c-498b-4c7a-a1ce-b571e37618bf.png)



**2.** Configuration DHCP server.

**1)** I installed DNSMASQ and configured DHCP server  
I added records to /etc/dnsmaskq.conf

![image](https://user-images.githubusercontent.com/42848618/147407506-74e831db-5679-4643-988c-98182682c08a.png)

I also disabled and stopped systemd-resolved service.

![image](https://user-images.githubusercontent.com/42848618/147408244-09a1e119-7f88-4787-b8e9-f4ac7e75d4b2.png)

I changed the network configuration of VM1.

![image](https://user-images.githubusercontent.com/42848618/147407899-b117dd42-9383-417f-ae04-18813a77f3f7.png)

**2)** I installed isc-dhcp-server and configured /etc/dhcp/dhcpd.conf file.

![image](https://user-images.githubusercontent.com/42848618/147409552-65eafcd1-7bd6-494d-95fd-718a5adee342.png)

I added interface to /etc/default/isc-dhcp-server.

![image](https://user-images.githubusercontent.com/42848618/147410067-f9ce433d-7859-4d43-ba6a-6b3d4fb9e70d.png)

I changed the network configuration and applied changes.

![image](https://user-images.githubusercontent.com/42848618/147410647-586fd780-d84f-45a5-a91c-e6a8371fea97.png)



**3.** I checked the results on VM2 and VM3.

For DNSMASQ

![image](https://user-images.githubusercontent.com/42848618/147407914-99d4fb2c-3155-44cb-abe5-9d39bb00a35f.png)

![image](https://user-images.githubusercontent.com/42848618/147407930-54fc8b8a-96e1-434b-bcd5-6afebb9033f9.png)

For ISC-DHCP-Server

![image](https://user-images.githubusercontent.com/42848618/147410295-59a81680-11a4-4b3b-8799-236579e71bc5.png)

![image](https://user-images.githubusercontent.com/42848618/147410324-06c8be7b-f936-4489-be6b-7db23f766a65.png)



**4.** I removed /etc/resolv.conf and added new one with record "nameserver 8.8.8.8" on VM1.

![image](https://user-images.githubusercontent.com/42848618/147416995-98efc99e-e18d-4988-96eb-15d5939ed4c0.png)

I added records into /etc/dnsmasq.conf

![image](https://user-images.githubusercontent.com/42848618/147417028-796d54e2-0483-4731-9031-1fefa5b7f586.png)

I added records of each vms to /etc/hosts on VM1.

![image](https://user-images.githubusercontent.com/42848618/147417067-58f8cbca-afde-4f8f-9fcb-3aa2380c53af.png)

Finally, I restarted dnsmasq service.

![image](https://user-images.githubusercontent.com/42848618/147417100-1cd42aff-1c33-4a10-951e-84b409bc7639.png)

I added "nameserver 10.10.10.1" into /etc/resolv.conf on VM2 and VM3.

![image](https://user-images.githubusercontent.com/42848618/147417151-4b35cafa-4ce6-4cfe-8667-2192e0917c7f.png)

![image](https://user-images.githubusercontent.com/42848618/147417172-185a0298-0e3b-4f54-b7a7-e6e187732ffa.png)



**5.**  See results of DNS configuration below.

![image](https://user-images.githubusercontent.com/42848618/147417280-81d7895d-6fad-4242-b31d-1b255446fdec.png)

![image](https://user-images.githubusercontent.com/42848618/147417324-dae5f1bf-ebe4-4f23-97b1-a03de51f96b4.png)



**6.** I configured OSPF for each vms.

I installed quagga to VM1 and created configuration files. I also change permissions on configuration files and created a directory of logs.
Finally, I started services.

![image](https://user-images.githubusercontent.com/42848618/147419086-b885b8e7-e626-4bfb-a5d2-62e1c5624309.png)

![image](https://user-images.githubusercontent.com/42848618/147419111-9ce92aeb-0ebc-4f66-aa2f-582a89fbda66.png)

![image](https://user-images.githubusercontent.com/42848618/147419139-4780005f-20de-4f8f-85c5-ee6a8244b9ea.png)

I did the same steps for VM2

![image](https://user-images.githubusercontent.com/42848618/147419488-a4dfb0da-8ad0-4b05-b4ac-2716c87aeac7.png)

and VM3.

![image](https://user-images.githubusercontent.com/42848618/147420680-869a8168-ca5d-4df6-872b-860b22b9a53e.png)



**7.** For showing results configuration I added route IP to VM3 and that route IP was automatically added for other vms. 

![image](https://user-images.githubusercontent.com/42848618/147420721-e90c558a-bf38-49ec-b9ce-d118f8eaabf1.png)

![image](https://user-images.githubusercontent.com/42848618/147420730-3c973ef3-d7af-43db-bcb9-b403f972b89e.png)

![image](https://user-images.githubusercontent.com/42848618/147420741-e75c4ba3-309e-4f15-8864-252d5ad66ed9.png)


