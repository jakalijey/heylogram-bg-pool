# Heylogram Domain Passport BG Pool

AI-generated background images for `.heylogramtv` NFT domain passports.

Each NFT picks its bg deterministically (hash of the domain name).

## Structure

```
core/    ← 22 fixed bg's for the FIRST 22 minted NFTs (tokenId 1–22).
         ← DO NOT add/remove/rename here — those NFTs would change image.

extra/   ← New bg's for tokenId 23+. Add as many as you want, any time.
         ← The NFT code auto-discovers this folder via jsDelivr.
```

## How to add new bg's

1. Generate PNG (any name you like, e.g. `mybg-001.png`, `tree-fire.png`).
2. Drop into `extra/`.
3. `git add extra/<file>.png && git commit -m "add" && git push`.
4. Wait 5–10 min for jsDelivr to mirror.
5. NEW domain mints (tokenId ≥ 23) will start picking from the enlarged pool automatically.

No code change needed on web3.jjvoi.com — the route reads the live `extra/` listing.

## Served via

[jsDelivr CDN](https://www.jsdelivr.com/) — sınırsız bandwidth, ücretsiz.

```
https://cdn.jsdelivr.net/gh/jakalijey/heylogram-bg-pool@main/core/<file>.png
https://cdn.jsdelivr.net/gh/jakalijey/heylogram-bg-pool@main/extra/<file>.png
```

Live listing JSON:
```
https://data.jsdelivr.com/v1/package/gh/jakalijey/heylogram-bg-pool@main
```

## Notes

- Supported formats: PNG, WebP, JPG (any one works).
- Recommended size: ~600x800 px (Heylogram passport viewBox). Larger wastes bandwidth.
- WebP is ~5× smaller than PNG at same quality. Recommended once pool grows beyond 100.
- jsDelivr has a 50MB per-file limit — keep individual bg's under that.

## License

Internal use only — Heylogram TV ecosystem.
