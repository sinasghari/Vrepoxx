





---

## نحوه‌ی کار (معماری)

```
┌──────────┐  TLS, SNI=vercel.com   ┌──────────────┐  HTTP/2   ┌──────────────┐
│  کلاینت   │ ─────────────────────► │ Vercel Edge  │ ────────► │  سرور Xray   │
│ (v2rayN/  │      XHTTP request     │  (relay)     │  forward  │ XHTTP inbound│
│  Hiddify) │                        │              │           │              │
└──────────┘                        └──────────────┘            └──────────────┘
```

1. کلاینت با SNI=`vercel.com` به دامنه‌ی Vercel وصل می‌شه. برای سانسورچی شبیه ترافیک عادی Vercel به‌نظر می‌رسه.
2. Vercel Serverless Function بدنه‌ی request رو **stream** می‌کنه به سرور Xray.
3. پاسخ هم به همون صورت stream می‌شه برمی‌گرده.

---

</div>

---


