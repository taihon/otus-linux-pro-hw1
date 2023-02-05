## OTUS Administrator Linux. Professional HW1
### **Решение**
```
wget https://cdn.kernel.org/pub/linux/kernel/v4.x/linux-4.19.271.tar.xz

tar xf linux-4.19.271.tar.xz

cp /boot/config-`uname -r` linux-4.19.271/.config
cd linux-4.19.271/
yes "" | make oldconfig 1>/dev/null
make -j$((`nproc`+1)) rpm-pkg 1>/dev/null
```

Далее устанавливаем собранные rpm-пакеты, меняем grub2-config, перезагружаемся.

До:
![before](./before_kernel_upgrade.png)
После:
![after](./after_kernel_upgrade.png)