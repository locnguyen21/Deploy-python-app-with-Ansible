# Deploy-python-app-with-Ansible
<h2> Mô tả các file bên trong </h2>

- ansible.cfg: file cấu hình ansible
- inventory: khai báo host triển khai service
- app.py: file ứng dụng python (chạy thư viện flask)
- deployapp.yml: file playbook triển khai cài đặt
- pyapp.service: file để cấu hình điều khiển app bằng systemd

<h2>Các bước trong playbook deploy app </h2>

- Cài đặt python3
- Cài đặt thư viện flask bằng pip3 sử dụng module "ansible.builtin.pip" của ansible
- Copy file python app vào các file host đã được khai báo trong inventory
- Copy file pyapp.service vào thư mục "/usr/lib/systemd/system" để systemd điều khiển app trong server ứng dụng, sử dụng module "copy" của ansible
- Reload lại daemon của systemd (systemd daemon reload) sau đó bật service (systemctl start pyapp), đồng thời enable ứng dụng sau khi server bị reboot, sử dụng module "service" của ansible

<h2>Lệnh triển khai</h2>

```
ansible-playbook -i inventory --ask-become-pass deployapp.yml
```
