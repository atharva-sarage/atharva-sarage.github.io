---
layout: page
title: Papershelf
permalink: /papershelf/
---

# 05/05/2025

[Recursive MakeConsidered Harmful](https://www.cse.iitd.ac.in/~sbansal/csp301/auug97.pdf)

## Key Points


### Sourcing a file.

When a script is sourced (using the . or source command), it inherits the positional parameters ($@, $1, $2, etc.) that were available in the calling shell's environment at the time of the sourcing. This means the sourced script can access and use these arguments as if they were passed directly to it. 

```sh
. auto/configure 

source auto/options 
```

[Nginx build system](https://github.com/nginx/nginx/blob/master/auto/configure)

#### Cool Tricks

1. heredoc

```bash

$ cat << END
> $0: This will write until 
> you see an .........
> END
-bash: This will write until
you see an .........
```

Here END is a delimitter



```
Nginx Reference /auto/have file.

# Copyright (C) Igor Sysoev
# Copyright (C) Nginx, Inc.


cat << END >> $NGX_AUTO_CONFIG_H

#ifndef $have
#define $have  1
#endif

END

```

# 08/05/2025

[The Slab Allocator:
 An Object-Caching Kernel Memory Allocator](https://srl.cs.jhu.edu/courses/600.418/SlabAllocator.pdf)

 1. Slab Allocator Deep dive week, one of my teammates implemented a slab allocator and that led to me reading their code 
    and also see how slab allocators work in linux.
1.  [Chapter 8 Slab Allocator](https://www.kernel.org/doc/gorman/html/understand/understand011.html)