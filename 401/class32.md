# Class 32 Reading Notes

## Permissions

Together with authentication and throttling, permissions determine whether a request should be granted or denied access.  

Permission checks are always run at the very start of the view, before any other code is allowed to proceed. Permission checks will typically use the authentication information in the request.user and request.auth properties to determine if the incoming request should be permitted. Permissions are used to grant or deny access for different classes of users to different parts of the API. The simplest style of permission would be to allow access to any authenticated user, and deny access to any unauthenticated user. This corresponds to the IsAuthenticated class in REST framework.

Permissions in REST framework are always defined as a list of permission classes.

Before running the main body of the view each permission in the list is checked. If any permission check fails, an exceptions.PermissionDenied or exceptions.NotAuthenticated exception will be raised, and the main body of the view will not run.

## Setting the permission policy

The default permission policy may be set globally, using the DEFAULT_PERMISSION_CLASSES setting.
```
REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.IsAuthenticated',
    ]
}
```
or
```
from rest_framework.decorators import api_view, permission_classes
from rest_framework.permissions import IsAuthenticated
from rest_framework.response import Response

@api_view(['GET'])
@permission_classes([IsAuthenticated])
def example_view(request, format=None):
    content = {
        'status': 'request was permitted'
    }
    return Response(content)
```

## API Reference

The `AllowAny` permission class will allow unrestricted access, regardless of if the request was authenticated or unauthenticated.

The `IsAuthenticated` permission class will deny permission to any unauthenticated user, and allow permission otherwise.

The `IsAdminUser` permission class will deny permission to any user, unless user.is_staff is True in which case permission will be allowed.



Reference [DRF Permissions](https://www.django-rest-framework.org/api-guide/permissions/)  
Reference [Review SQL Prework](https://codefellows.github.io/common_curriculum/prework/SQL)

## Things I want to know more about

[Back to Home](../../README.md)
