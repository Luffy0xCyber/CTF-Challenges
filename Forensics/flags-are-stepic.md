
# Description 

A group of underground hackers might be using this legit site to communicate. Use your forensic techniques to uncover their message

Additional details will be available after launching your challenge instance. (http://standard-pizzas.picoctf.net:60820/) 


# Write Up 


I visited the website: `http://standard-pizzas.picoctf.net:60820/` and noticed a grid filled with country flags. However, one flag stood out a **non-existent country** named _"Upanzi, Republic The"_.

After inspecting the `index.html`, I found that this flag corresponds to the image located at `flags/upz.png`. So, I navigated to `http://standard-pizzas.picoctf.net:60820/flags/upz.png` and downloaded the image.

I tried several tools including `strings`, `exiftool`, `binwalk`, and `stegsolve`, but didn’t find anything conclusive.

However, the **title of the challenge** was a major hint _"flags are stepic"_ suggesting the use of the **Stepic** steganography tool.

So I installed `stepic` and ran the following command:

```
stepic -d -i upz.png -o response.txt
```

Then I simply ran `cat response.txt`, and there it was — **the flag**!

# Flag 

picoCTF{fl4g_h45_fl4g16aa94cf}                                                                              