# Cài đặt Heat Dashboard 

Trước khi cài đặt Heat Dashboard cần cài Horizon trước tham khảo cài đặt Horizon tại https://docs.openstack.org/horizon/queens/install/install-ubuntu.html

Cài đặt packages Heat Dashboard

``` sh
pip install heat-dashboard
```
``` sh
sudo apt-get install gettext
```

Các packages sẽ được cài vào thư mục `/usr/lib/python2.7/dist-packages/heat-dashboard`


Để có thể enable heat-dashboard plugin bạn cần phải copy các file trong thư mục `/usr/lib/python2.7/dist-packages/heat_dashboard/enabled/_[1-9]*.py` vào trong thư mục `/usr/share/openstack-dashboard/openstack_dashboard/local/enabled`

``` sh
cp /usr/lib/python2.7/dist-packages/heat_dashboard/enabled/_[1-9]*.py \
      /usr/share/openstack-dashboard/openstack_dashboard/local/enabled
```

Copy file sau vào thư mục heat-dashboard

``` sh
cp /usr/share/openstack-dashboard/./manage.py /usr/lib/python2.7/dist-packages/heat_dashboard/
```

Trên command line di chuyển tới thư mục heat-dashboard:

`cd /usr/share/openstack-dashboard/`

Chạy từng dòng lệnh sau:

``` sh
python ./manage.py compilemessages
DJANGO_SETTINGS_MODULE=openstack_dashboard.settings python manage.py collectstatic --noinput
DJANGO_SETTINGS_MODULE=openstack_dashboard.settings python manage.py compress --force
```
 
 
Khởi động lại dịch vụ apaches: 

`sudo service apache2 restart`

Trên giao diện màn hình đăng nhập :

<img src="https://github.com/anhict/Openstack-Heat/blob/master/images/heat3.png">


<img src="https://github.com/anhict/Openstack-Heat/blob/master/images/heat4.png">


<img src="https://github.com/anhict/Openstack-Heat/blob/master/images/heat5.png">

Sử dụng các thành phần có sẵn để tạo subnet,router ...

<img src="https://github.com/anhict/Openstack-Heat/blob/master/images/heat6.png">


<img src="https://github.com/anhict/Openstack-Heat/blob/master/images/heat7.png">

 
Click chuột trái 1 lần vào icon và điền các thông số :

<img src="https://github.com/anhict/Openstack-Heat/blob/master/images/heat8.png">

Sử dụng ADD EDGE để tạo các kết nối giữa các thành phần:

<img src="https://github.com/anhict/Openstack-Heat/blob/master/images/heat9.png"> 


<img src="https://github.com/anhict/Openstack-Heat/blob/master/images/heat10.png">

<img src="https://github.com/anhict/Openstack-Heat/blob/master/images/heat11.png">


<img src="https://github.com/anhict/Openstack-Heat/blob/master/images/heat12.png">

<img src="https://github.com/anhict/Openstack-Heat/blob/master/images/heat14.png">

<img src="https://github.com/anhict/Openstack-Heat/blob/master/images/heat15.png">

<img src="https://github.com/anhict/Openstack-Heat/blob/master/images/heat16.png">

<img src="https://github.com/anhict/Openstack-Heat/blob/master/images/heat17.png">

<img src="https://github.com/anhict/Openstack-Heat/blob/master/images/heat18.png">

<img src="https://github.com/anhict/Openstack-Heat/blob/master/images/heat19.png">

<img src="https://github.com/anhict/Openstack-Heat/blob/master/images/heat20.png">

<img src="https://github.com/anhict/Openstack-Heat/blob/master/images/heat21.png">

<img src="https://github.com/anhict/Openstack-Heat/blob/master/images/heat22.png">






























Tài liệu tham khảo : 


https://docs.openstack.org/heat-dashboard/latest/install/index.html


https://www.youtube.com/watch?v=tv-9DzCEulo