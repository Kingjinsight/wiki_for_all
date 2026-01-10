## Tips

1. Access remote services (like Jupyter Notebook or web servers) on your local machine through SSH tunneling.

```ssh -L [local_port]:localhost:[remote_port] username@remote_server```

2. Solve zsh causing duplicate characters when ssh into the server

```infocmp -x | ssh <username>@<your server ip> -- tic -x - ```
