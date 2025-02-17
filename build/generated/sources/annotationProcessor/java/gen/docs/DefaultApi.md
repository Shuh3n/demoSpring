# DefaultApi

All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**registerUser**](DefaultApi.md#registerUser) | **POST** /users | Registrar un nuevo usuario |
| [**updateUserPassword**](DefaultApi.md#updateUserPassword) | **PATCH** /users/{id}/password | Actualizar la contraseña de un usuario |


<a id="registerUser"></a>
# **registerUser**
> UserResponse registerUser(userRegistration)

Registrar un nuevo usuario

### Example
```java
// Import classes:
import org.openapitools.client.ApiClient;
import org.openapitools.client.ApiException;
import org.openapitools.client.Configuration;
import org.openapitools.client.models.*;
import org.openapitools.client.api.DefaultApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");

    DefaultApi apiInstance = new DefaultApi(defaultClient);
    UserRegistration userRegistration = new UserRegistration(); // UserRegistration | 
    try {
      UserResponse result = apiInstance.registerUser(userRegistration);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DefaultApi#registerUser");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **userRegistration** | [**UserRegistration**](UserRegistration.md)|  | [optional] |

### Return type

[**UserResponse**](UserResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Usuario registrado exitosamente |  -  |
| **400** | Datos de entrada inválidos |  -  |
| **409** | Correo ya registrado |  -  |
| **500** | Error interno del servidor |  -  |
| **503** | Servicio no disponible |  -  |

<a id="updateUserPassword"></a>
# **updateUserPassword**
> UserResponse updateUserPassword(id, successResponse)

Actualizar la contraseña de un usuario

### Example
```java
// Import classes:
import org.openapitools.client.ApiClient;
import org.openapitools.client.ApiException;
import org.openapitools.client.Configuration;
import org.openapitools.client.auth.*;
import org.openapitools.client.models.*;
import org.openapitools.client.api.DefaultApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    DefaultApi apiInstance = new DefaultApi(defaultClient);
    String id = "id_example"; // String | 
    SuccessResponse successResponse = new SuccessResponse(); // SuccessResponse | 
    try {
      UserResponse result = apiInstance.updateUserPassword(id, successResponse);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DefaultApi#updateUserPassword");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **String**|  | |
| **successResponse** | [**SuccessResponse**](SuccessResponse.md)|  | [optional] |

### Return type

[**UserResponse**](UserResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Contraseña actualizada exitosamente |  -  |
| **400** | Datos de entrada inválidos |  -  |
| **401** | No autorizado |  -  |
| **403** | Prohibido (sin permisos suficientes) |  -  |
| **404** | Usuario no encontrado |  -  |
| **500** | Error interno del servidor |  -  |
| **503** | Servicio no disponible |  -  |

