# Django basic setting

## 1. Authentication project-level permissions

```Python
# project/settings.py
REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.AllowAny',
    ]
}
```

Với

- `AllowAny`: Tất cả các user, không có auth vẫn có full quyền với API
- `IsAuthenticated`: Chỉ có authenticated, registered user mới có quyền truy cập
- `IsAdminUser`: Chỉ admins/superusers có quyền truy cập API
- `IsAuthenticatedOrReadOnly`: users không có auth thì chỉ có thể view api, chỉ có users có auth thì mới có thể ghi, sửa, xóa

## 2. Base class for rest_framework views

- `APIView`: Sử dụng để customize các api request
- `viewsets.ModelViewSet`: Sử dụng khi alloww tất cả CRUD api
- `generics.*subclasses`: Sử dụng khi chỉ allow một số api method

## 3. Deployment