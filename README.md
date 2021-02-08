# wsServer
forked from [here](https://github.com/Theldus/wsServer).
The only difference is that onopen() has a different signature:

```c
void onopen(int fd, char *path);
```

Passing the path from the opening HTTP request.
That path needs to be free()d in the onopen handler.

I hacked this together because I needed that functionality.