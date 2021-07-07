# Two-Factor Authentication

Github supports [two-factor
authentication](https://github.com/settings/two_factor_authentication/configure),
and it is highly recommended that you set it up for your account.

## Why?

The basic idea behind two-factor authentication is that proving you *know*
something (your password) and that you *have* something (your phone) is harder
than just proving you know your password. Thus there are apps for your phone
that implement *one time password* (OTP) algorithms, which generate a
hard-to-guess sequence of codes that means only somebody who managed to break
into your phone can pretend to be you.

* FreeOTP on [iOS](https://itunes.apple.com/us/app/freeotp/id872559395) and
[Android](https://play.google.com/store/apps/details?id=org.fedorahosted.freeotp)
* [2FA](https://www.microsoft.com/en-us/store/apps/2fa/9wzdncrcw1jr) on Windows

## No, *why*?

Because code can sometimes be important, and part of what version control does
is track who did what. If somebody can pretend to be you, they can make it look
like you did bad things to important code. And Github's a social network. They
can make you look like a jerk.
