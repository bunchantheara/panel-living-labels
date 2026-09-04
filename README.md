# Panel Living label printer

Prints QR price labels for **Panel Living, 2Sister and TU Cabinet** from one
page. Live at <https://bunchantheara.github.io/panel-living-labels/>.

## Printing

**Make PDF → download → import into NiceLabel → print.** That is the proven
route. Printing straight from Chrome works too, but only with the paper size
matching the page and **Scale = Actual size** — "Fit to paper" stretches the
page and throws every label off.

Each PDF page carries its own size, so the page size itself cannot be got
wrong; only the scale setting can.

## Current stock

Single-column **40 × 30 mm** labels, one label per PDF page. The whole roll is
editable on the page — label width and height, labels across, the gaps and the
liner edge — with a live summary of what they add up to. A stock change needs
no code.

## Layout

QR on the left, price to its right, SKU across the full width beneath, on one
or two lines. SKU and price both bold.

The page sizes itself to the content: it picks the number of SKU lines and the
type size from the longest SKU in the run, and lets the QR trade size for
readable text down to a floor. Whatever it decides is reported on screen, and
it warns if a QR would fall below three printer dots per module — the point
where it stops scanning reliably at 203 dpi.

## Where labels come from

- The **Print Label** button in Zoho Books, which opens the page with the item
  in the URL fragment: `#sku=...&price=...&product_name=...`. The fragment is
  never sent to a server, so SKUs and prices stay out of request logs.
- Or paste a SKU list or a Books CSV export directly into the page.

## Notes

QR codes are generated in the browser by qrcode-generator (Kazuhiko Arase,
MIT), inlined so the page needs no network access once loaded. SKUs encode in
Alphanumeric mode, which keeps them a QR version smaller — and therefore the
modules larger — than the library's Byte default.

The QR contains the bare SKU, exactly as the old zohoprintengine labels did, so
old and new stock scan identically.
