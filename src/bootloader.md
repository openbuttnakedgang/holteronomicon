# Загрузчик

Загрузчик использует DFU USB спецификацию [Device Firmware Upgrade](http://www.usb.org/developers/docs/devclass_docs/DFU_1.1.pdf),
широко распространенный стандарт, применяющийся для обновления прошивок разнообразных устройств.

Благодаря этому для обновления прошивки достаточно использовать стандартные утилиты для работы с DFU (например: [dfu-util](http://dfu-util.sourceforge.net/)). 

### WebUSB
Загрузчик осуществляет поддержку драфта [WebUSB](https://wicg.github.io/webusb/) спецификации,
что позоволяет веб-страницам осуществлять доступ к загрузчику (после выбора устройства в юзер-экшен диалоге).

[Демо страница для работы с загрузчиком](https://devanlai.github.io/webdfu/dfu-util/)

### Требования WebUSB к хосту
The current WebUSB draft no longer requires the device to support additional WebUSB descriptors.
However, implementing WebUSB descriptors allows the device to specify a landing page URL for the browser to present to the user when the device is plugged in.

For an example WebUSB-enabled USB DFU bootloader for the STM32F103 series, check out the [dapboot](https://github.com/devanlai/dapboot) project



## TODO:..