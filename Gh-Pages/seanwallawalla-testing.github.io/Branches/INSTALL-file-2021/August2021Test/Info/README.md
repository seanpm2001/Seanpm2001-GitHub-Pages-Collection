
***

# 2021 August GitHub pages test

## Info

In 2021 August, I went through another set of changes to the way I make projects. I didn't find until a few days later that it is incompatible with GitHub pages. Frustratingly, I don't even get a good error message that tells me what went wrong. It fails in 0 seconds and just says "GitHub pages failed to build your site"

So I am going to test here, by hand, on ring 2 of GitHub pages development what went wrong, and will keep trying until I can build the site. For the mean time, this site may go offline due to build errors.

It is either 1 or more of the following 7 files that are at fault:

`.editorconfig`

`.gitattributes`

`.gitignore`

`copying` / `copyingl` MIME: text/x-copying

`credits`

`install`

`makefile.mk`

I have to figure out which file is causing the failure, and fix the problem, then I will continue on with the build process.

For future use, this branch is going to go stale, but I am going to keep it for legacy and archival purposes.

## Conclusion

Conclusion: the file `INSTALL` was the problem. Even changing it to have a file extension still caused it to fail. Right now, the only way I can correct the problem is by not including it under its current name. I just tested all 7 files individually and have rooted this as the cause. I will release a patch tomorrow.

### Further difficulty

After several workarounds, I found that GitHub pages seems to REALLY hate something about how this file is written. I tried changing the name to `INSTALLATION_INSTRUCTIONS_FILE` `INTSTALL` `iSTALL` and `HOWTO` and even tried replacing all instances of the word `install` to `build` but every attempt caused the site to fail to build. I am going to need to do more research on this.

***
