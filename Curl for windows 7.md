## Vấn đề
Từ windows 10 trở lên thì trong cmd sẽ tích hợp sẵn câu lệnh curl.

Windows 7 trở xuống thì trong cmd không có sẵn câu lệnh curl.

(Windows 8 và các người anh em của Linux thì không rõ)

## Giải pháp
Để chạy được lệnh curl thì ta cần cài riêng chương trình curl [tại đây](https://curl.se/windows/)

Giải nén file vừa tải rồi để ở đâu đó, ví dụ: D:\Downloads\curl-8.4.0_6-win64-mingw

Thêm D:\Downloads\curl-8.4.0_6-win64-mingw\bin vào 'Path' trong 'Environment Variables'

Bây giờ thì đoạn code python sau (có sử dụng curl) đã có thể chạy được

    import subprocess
    
    result = subprocess.check_output('curl www.google.com', shell=True,
                                     universal_newlines=True)
    
    print(result)
