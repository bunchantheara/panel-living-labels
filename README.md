# Panel Living label printer

Prints 35 x 20 mm QR labels, two across a 73 mm die-cut roll row.

Opened by the **Print Label** button in Zoho Books, which passes the item in the
query string: `?product_name=...&price=...&sku=...` (plus optional `copies=N`
and `autoprint=1`). Can also be opened directly and given a pasted SKU list or a
CSV export.

QR codes are generated in the browser by qrcode-generator (Kazuhiko Arase, MIT),
inlined so the page needs no network access once loaded.
