# File System Cache

## Linux Commands
* cat /proc/meminfo
* sync
* free -m

## Sources:
* [Linux System Administrators Guide](http://www.tldp.org/LDP/sag/html/buffer-cache.html)

    Reading from a disk is very slow compared to accessing (real) memory.
    In addition, it is common to read the same part of a disk 
      several times during relatively short periods of time....
    By reading the information from disk only once 
      and then keeping it in memory until no longer needed, 
      one can speed up all but the first read. 
    This is called disk buffering, 
      and the memory used for the purpose is called the buffer cache.

    Most operating systems have buffer caches (although they might be called something else)...
    Some are write-through: the data is written to disk at once 
      (it is kept in the cache as well, of course). 
    The cache is called write-back if the writes are done at a later time. 

    Write-back is more efficient than write-through, but also a bit more prone to errors: 
      if the machine crashes, 
        or the power is cut at a bad moment, 
        or the floppy is removed from the disk drive before 
          the data in the cache waiting to be written gets written,
      the changes in the cache are usually lost. 
      
      **This might even mean that the filesystem (if there is one) is not in full working order, 
        perhaps because the unwritten data held important changes to the bookkeeping information.**



* [Linux ate my ram!](http://www.linuxatemyram.com/)
* [Linux Page Cache Basics](https://www.thomas-krenn.com/en/wiki/Linux_Page_Cache_Basics)
* [Straylight Run: Clearing The Linux Buffer Cache](http://blog.straylightrun.net/2009/12/03/clearing-the-linux-buffer-cache/)
* [Improving Linux performance by preserving Buffer Cache State](http://insights.oetiker.ch/linux/fadvise.html)
* [Examining Linux 2.6 Page-Cache Performance](http://www.linuxinsight.com/files/ols2005/rao-reprint.pdf)
* [Page cache](https://en.wikipedia.org/wiki/Page_cache)
* [The Linux Storage Stack Diagram](https://upload.wikimedia.org/wikipedia/commons/3/30/IO_stack_of_the_Linux_kernel.svg)
* [Can I configure my Linux system for more aggressive file system caching?](http://unix.stackexchange.com/a/41831)
* [fadvise(2) - Linux man page](http://linux.die.net/man/2/fadvise)
* [Understand Linux Virtual Memory Management](http://www.enterprisenetworkingplanet.com/netsysm/article.php/3741281/Understand-Linux-Virtual-Memory-Management.htm)
* [/kernel/Documentation/sysctl/vm.txt](http://www.mjmwired.net/kernel/Documentation/sysctl/vm.txt)
