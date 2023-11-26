# Deploy-python-app-with-Ansible
<h2> Mô tả các file bên trong </h2>
- ansible.cfg: file cấu hình ansible
- inventory: khai báo host triển khai service
- app.py: file ứng dụng python (chạy thư viện flask)
- deployapp.yml: file playbook triển khai cài đặt
- pyapp.service: file để cấu hình điều khiển app bằng systemd
Các bước trong playbook
