# wsServer
forked from [here](https://github.com/Theldus/wsServer).
The only difference is that onopen() has a different signature:

```c
void onopen(int fd, char *path);
```

Passing the path from the opening HTTP request.
That path needs to be free()d in the onopen handler.

Additionally, there are two more functions for closing connections:
```c
int ws_close(int fd, short code, const char *data, size_t len);
int ws_close_msg(int fd, short code, const char *message);
```

I hacked this together because I needed that functionality.