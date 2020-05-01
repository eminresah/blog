---
title: TIL May 1 
author: Emre Şahin
date:  2020-05-02 01:19:07 +03
dp: 14901
draft: false
---


- [Nota](https://kary.us/nota/) seems a nice command line calculator. It converts what you type into
    ASCII art formulas. 


```
  In[1]: 10 + 10

 Out[1]: 20.0


           _____
  In[2]: ╲╱ 100

 Out[2]: 10.0


             ┌                  ┐
  In[3]: Max │ 10 , 1 , 21 , -3 │
             └                  ┘

 Out[3]: 21.0


  In[4]: ⟨Emre's Number⟩ ≡  79

 Out[4]: 79.0


           _______________
  In[5]: ╲╱ Emre's Number

 Out[5]: 8.888194417315589


                      2
  In[6]: Emre's Number

 Out[6]: 6241.0


                      Emre's Number
  In[7]: Emre's Number

 Out[7]: 8.1759873707105095e149

```

    It looks a bit heavy for a CLI calculator, due to the fact that it's written in Haskell and downloaded 100+ MB of libraries but when you need ASCII art to show your calculations and use spaces in variables, it may prove useful. 


- I began to use [Intention](https://www.getintention.com/) to limit my Twitter time. It allows to
    set a limited time (1-5-10-15 minutes) for yourself occasionally and checks the total time you
    spent in *addictive sites.* When this total time is lower than your goal for a period, you get a
    streak. Looks visually and psycologically nicer than LeechBlock. 

- I read the [`git reset`](http://www.git-scm.com/book/en/v2/Git-Tools-Reset-Demystified) section in
    the git book. It details how `git reset` behaves with its `--soft`, `--mixed` and `--hard`
    parameters. The first resets only the `HEAD`, the second both index and `HEAD` and the third
    resets working tree and copies files back from current `HEAD` to the working tree. 

    One important point: Contrasting `git checkout master` and `git reset master`: The first moves `HEAD` to `master` branch and the second moves current branch to `master`.

    `git reset` can also be used to squash commits into one. Basically you `git reset --mixed` to an
    earlier branch like `HEAD~3` and recommit. This creates a new commit, taking `HEAD~3` as parent
    and skipping `HEAD~2`, `HEAD~1` with a new `HEAD`

- [Here](https://github.com/dylanaraps/pure-bash-bible) there are many useful pure bash functions to
    be used in scripts. I'm a zsh person but writing bash scripts is more portable, of course. 
