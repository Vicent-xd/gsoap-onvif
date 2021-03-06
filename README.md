Notes:

automake --add-missing
autoreconf
sudo apt-get install bison flex
https://gitweb.gentoo.org/repo/gentoo.git/tree/net-libs/gsoap/files/gsoap-2.8.93-fix-parallel-build.patch?id=e035a4bf9fbd9853270a0a665ea80f59009b060d
./configure --disable-ssl

4.2 onvif.h文件生成
cd bin/
wsdl2h -c -t ../typemap.dat -o onvif.h ./wsdl/devicemgmt.wsdl ./wsdl/event.wsdl ./wsdl/media.wsdl ./wsdl/ptz.wsdl

#import "wsse.h" >> onvif.h

4.3 c文件生成
soapcpp2 -c -x onvif.h -I ../ -I ../import -I ../custom

cp *.nsmap onvif
cp *.c onvif
cp *.h onvif

openssl-1.0.2r.tar.gz


url:https://www.onvif.org/profiles/specifications/
url:http://blog.leanote.com/post/jluyeyu/Onvif对应的不同

# Onvif的wsdl文档地址
## DeviceMgmt（设备管理）
https://www.onvif.org/ver10/device/wsdl/devicemgmt.wsdl 

## DeviceIO（设备IO服务）
http://www.onvif.org/onvif/ver10/deviceio.wsdl

## Event（事件处理）
http://www.onvif.org/onvif/ver10/event/wsdl/event.wsdl

## Analytics（视频分析）
http://www.onvif.org/onvif/ver20/analytics/wsdl/analytics.wsdl

## AnalyticsDevice（分析设备）
http://www.onvif.org/onvif/ver10/analyticsdevice.wsdl

## Display（显示服务）
http://www.onvif.org/onvif/ver10/display.wsdl

## Imaging（图像配置）
http://www.onvif.org/onvif/ver20/imaging/wsdl/imaging.wsdl

## Media（媒体配置）
https://www.onvif.org/ver10/media/wsdl/media.wsdl

## PTZ（PTZ控制）
http://www.onvif.org/onvif/ver20/ptz/wsdl/ptz.wsdl

## Receiver（接收端配置）
http://www.onvif.org/onvif/ver10/receiver.wsdl

## RemoteDiscovery（设备发现）
https://www.onvif.org/ver10/network/wsdl/remotediscovery.wsdl

## Recording（录像控制）
http://www.onvif.org/onvif/ver10/recording.wsdl

## Replay（重放控制）
http://www.onvif.org/onvif/ver10/replay.wsdl

## Search（记录搜索）
http://www.onvif.org/onvif/ver10/search.wsdl

# 对应各模块文档：
https://www.onvif.org/onvif/ver20/util/operationIndex.html
