# Drive Traffice Version SP

## Tất cả component cho sp viết ở đây:	
	/resources/assets/typescript/sp/
- Khai báo component, services, directive trong AppModule của SP: **app-sp.module.ts**
- wireframe:
   ![alt text](https://docs.google.com/drawings/d/107XOIzitgdibAsLQtvsYN2yOawTK6oWPbnSLyMDXvxw/pub?w=745&amp;h=687)
- Dev chỉ cần code cho phần chức năng chính để  apply vào **Router Outlet** 
- Phần còn lại sẽ  được quản lý bởi MainServices (xem tiếp phần main.service.ts bên dưới)
## Ngoài ra các service, directive, pipe viết ở các folder tương ứng:
	/resources/assets/typescript/services
	/resources/assets/typescript/pipes
	/resources/assets/typescript/directives
# Một số service dùng chung:
#### Main Service 
	/resources/assets/typescript/services/main.service.ts

- Quản lý hiển thị: header, search, tabs, title.
- Các hàm chính:
```javascript
setLayoutProps(option);
    default: hiển thị title, search, tabs
    {
        title: '',
        back_title: '',
        back_link: '',
        hide_title: false,
        hide_search: false,
        hide_tabs: false,
        hide_back: true
    }
```
> ví dụ: trang Login cần ẩn tabs và search:
```javascript
    ngOnInit() {
        this.mainService.setLayoutProps({
            title:'マイルート会員登録',     // title tương ứng
            hide_search:true,           // ẩn search
            hide_tabs:true              // ẩn tabs
        })
    }
```
#### Map Service 
	/resources/assets/typescript/services/map.service.ts
- Sử dụng bằng cách import như các service khác.
- Tất cả hàm từ PC vẫn giữ nguyên.
- Các hàm mới bổ sung:
    + showMap
	+ hideMap
	+ showPopup
	+ hidePopup
```javascript
    this.mapService.showMap()
```
___

![alt text](https://docs.google.com/drawings/d/1DNysEHAI-F3XAQ8ksrVc95M6ud4Ruf-NTcmGQlAy3bw/pub?w=387&amp;h=713)