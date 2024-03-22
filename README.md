# WebRequest-MQL5 

(This is the forked repo with English translated from the original one, everything else is the same)
WebRequest-MQL5 is an MQL5 library that offers a simple and effective interface for communication with web servers using the HTTP protocol. With this library, developers can easily perform HTTP GET, POST, PUT, DELETE, and other requests, as well as send and receive data securely and efficiently.

Making the integration of algorithmic trading applications with external web services easy. With an intuitive interface and comprehensive documentation, WebRequest-MQL5 simplifies the process of communicating with web servers, providing MQL5 developers with a powerful tool for remote access to data and web services.

The library is composed of an architecture that allows for mocking of each class, thus making it possible to perform unit tests without depending on responses from HTTP requests.

## 🔧 Features

- Sending of HTTP GET, POST, PUT, DELETE requests and other methods.
- Support for JSON format for sending and receiving data
- Support for secure communication through HTTPS.
- Complete documentation and usage examples.

## 📖 Installation Guide

1. Open the Data folder of your Metatrader5 terminal
2. Navigate to `MQL5/Includes`
3. Clone the project inside the `/Includes` folder of your Metatrader5 Terminal
``` shell
git clone https://github.com/github-joao-pedro/WebRequest-MQL5.git
```

## 👨🏻‍💻 Usage Example

Here is a simple example of how to use the library to make an HTTP GET request to the Binance API
``` c++
#include <WebRequest-MQL5/Http/HttpClient.mqh>

void OnStart()
  {
   //--- Creates request/order/response objects
   CHttpClient client;
   CHttpRequest request;
   CHttpResponse response;

   //--- Defines method used and URL
   request.Request(HTTP_METHOD_GET,"https://api.binance.com/api/v3/avgPrice?symbol=BTCUSDT");
   
   //--- Checks if request was made successfully
   if(client.Send(request,response))
     {
      //--- Prints results
      Print("REQUEST  | ",request.Method().HttpMethodsDescription()," - ",request.Url().Serialize());
      Print("RESPONSE | ",response.Body().Serialize());
     }
  }
```

```
REQUEST  | GET - https://api.binance.com:443/api/v3/avgPrice?symbol=BTCUSDT
RESPONSE | {"mins":5,"price":"45358.93311660","closeTime":1707438768533}
```

## 🔗 Dependencies
This project depends on the following library:

- [CJAVal](https://www.mql5.com/en/code/13663) - JSON Serialization and Deserialization (MQL native)

## 📄 Documentation
The [documentation](https://joaopedrodev.notion.site/WebRequest-MQL5-221944146357478b9a01ade899e2531b) complete with the library's functions is available and under construction, but can already be accessed.

## 🤝 Contributing

Contributions are welcome!

Feel free to open an issue or send a pull request with improvements or corrections.

## 📝 License

The WebRequest-MQL5 library is released under the MIT license. See [LICENSE](./LICENSE) for details.
