# Redis
<h4>Create table employee:1 Redis</h4>

<h4>Add attribute start_time employee:1 Redis</h4>


```bash
HSET employee:1 start_time "2024-05-19 08:00:00"
```


<h4>Add attribute start_time employee:1 Redis</h4>


```bash
HSET employee:1 end_time "2024-05-19 17:00:00"
```


<h4>Add attribute total_amount employee:1 Redis</h4>


```bash
HSET employee:1 total_hours 9.0
```


<h4>Update redis in docker by bash script</h4>

```bash
#!/bin/bash

# Hàm để cập nhật thời gian bắt đầu làm việc của một nhân viên
update_start_time() {
    employee_id=$1
    current_time=$(date "+%Y-%m-%d %H:%M:%S")
    docker exec bcb827f2672c redis-cli HSET "employee:$employee_id" start_time "$current_time"
}

# Vòng lặp vô hạn để cập nhật thời gian bắt đầu làm việc của tất cả các nhân viên mỗi giây
while true; do
    # Gọi hàm update_start_time cho mỗi nhân viên (ví dụ: employee_id 1 và 2)
    update_start_time 1
    update_start_time 2
    
    # Sleep 1 giây trước khi tiếp tục vòng lặp
    sleep 1
done
```
