# Hackintosh-Dell-OptiPlex 9020M

- Đã test với Big Sur 11.6.1, Catalina 10.15.7 
- Một số hình ảnh về Big Sur trên Dell OptiPlex 9020M

Info

![Screen Shot 2021-10-07 at 12 21 51](https://user-images.githubusercontent.com/92006941/136325524-f392d196-9482-49cb-82cd-94a01dd53af3.png)

Phiên bản OpenCore BootLoader 0.7.5 (ảnh minh hoạ đã cũ)

![Screen Shot 2021-10-07 at 12 22 22](https://user-images.githubusercontent.com/92006941/136325624-b2cb6a9d-bb6a-46db-b380-f74b09012936.png)

Map USB thành công sẽ trông như này

![Screen Shot 2021-10-07 at 12 22 33](https://user-images.githubusercontent.com/92006941/136325667-dfa57305-4b55-4908-8a6b-a42be2d8701b.png)

Imessage hoạt động OK

![Screen Shot 2021-10-07 at 12 27 05](https://user-images.githubusercontent.com/92006941/136325705-bc80bad7-12a8-4a44-8d9c-9d83090a1382.png)

## Thông số phần cứng

- Barebone Chassis: [Dell OptiPlex 9020M](https://www.hardware-corner.net/desktop-models/Dell-OptiPlex-9020M) với 1 port DP và 1 port VGA
- CPU: Intel® Core™ i5-4590T
- iGPU: Intel® HD Graphics 4600
- RAM 8GB DDR3 1600MHz
- SSD: NT-256-TI
- Ethernet: I217-LM
- Wi-Fi & Bluetooth: AC-7260


## Hướng dẫn sử dụng

  **Setup Bios**
  
  **1. Hãy tắt, bỏ chọn những mục sau: (DISABLE)**  
   - Secure Boot → Secure Boot Enable: Disabled
   - Virtualization Support → VT for Direct I/O: Bỏ chọn

  **2. Hãy bật, chọn những mục sau: (ENABLE)**
   - System Configuration → SATA Operation: AHCI
   - Virtualization Support → Virtualization: chọn
   
  **Lưu ý**

  - Bạn cần thay đổi SMBIOS phù hợp với máy của mình bằng [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) sau đó có thể thử boot mà không cần chỉnh gì thêm, nếu gặp lỗi hãy đến với phần [Thay đổi](https://github.com/HowNeft/HowNeft.github.io#thay-%C4%91%E1%BB%95i).

  **Thay đổi**

  1. Nếu gặp lỗi khi boot, Tiếp theo map usb theo cách sau: [Map USB](https://vietnamitx.com/t/mapping-usb-port-hackintosh-de-dang-don-gian-nhat-2021.206/) (làm theo hướng dẫn để map lại USB bên window ). Sau đó, xoá Kext USBPorts.kext và ACPI -> SSDT SSDT-UIAC.aml, thêm kext như bên hướng dẫn Map usb và snap lại config nhé.
  2. Đối với vấn đề iservice như imess/facetime, bạn cần call / nhắn tin với apple để kích hoạt ID Apple kích hoạt
  3. Nếu sleep gặp vấn đề, hãy tham khảo [tại đây](https://github.com/ismethr/9020mHack)

# LINK DOWNLOAD:
 **[Bấm vô đây bạn ơi](https://github.com/HowNeft/Optiplex9020M/releases/tag/Release)**
