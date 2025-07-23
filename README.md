Perfect! Here's the **updated `README.md`** with all examples rewritten in **JavaScript**, ideal for frontend or Node.js developers consuming your nested JSON dataset.

---

````markdown
# 🇳🇬 Nigeria States, LGAs, and Wards Dataset

An open and structured dataset of **Nigeria's 36 States**, **774 Local Government Areas (LGAs)**, and their **electoral Wards**, organized in a deeply nested JSON format.

This resource is ideal for developers, civic tech projects, geospatial tools, address validation, and administrative systems in Nigeria.

---

## 🗂 Data Format

The main dataset is a single JSON file with the following structure:

```json
[
  {
    "state": "Abia",
    "lgas": [
      {
        "lga": "Aba North",
        "wards": [
          "Ariaria Market",
          "Eziama",
          "Industrial Area",
          "Ogbor I",
          "Ogbor Ii",
          "Old Aba Gra",
          "Osusu I",
          "Osusu Ii",
          "St Eugenes By Okigwe Rd",
          "Umuogor",
          "Umuola",
          "Uratta"
        ]
      }
    ]
  }
]
````

Each state contains an array of LGAs, and each LGA contains an array of its wards.

---

## 📁 Files

| File                                  | Description                                        |
| ------------------------------------- | -------------------------------------------------- |
| `data/nigeria-states-lgas-wards.json` | Full nested dataset in JSON format                 |
| `scripts/flatten.js` (optional)       | Script to flatten JSON into tabular format         |
| `data/lgas.csv` (optional)            | Flattened table of LGAs for spreadsheet use        |
| `data/wards.csv` (optional)           | Flattened table of all wards with parent state/LGA |

---

## 🔍 Sample Usage

### ✅ JavaScript – Print all wards with their state and LGA (Node.js)

```js
const fs = require('fs');

const data = JSON.parse(fs.readFileSync('data/nigeria-states-lgas-wards.json', 'utf8'));

data.forEach(state => {
  state.lgas.forEach(lga => {
    lga.wards.forEach(ward => {
      console.log(`${state.state} → ${lga.lga} → ${ward}`);
    });
  });
});
```

### 🌐 JavaScript – Fetch and display in browser (Frontend)

```html
<script>
fetch('https://raw.githubusercontent.com/your-username/nigeria-states-lga-wards/main/data/nigeria-states-lgas-wards.json')
  .then(response => response.json())
  .then(data => {
    data.forEach(state => {
      state.lgas.forEach(lga => {
        lga.wards.forEach(ward => {
          console.log(`${state.state} → ${lga.lga} → ${ward}`);
        });
      });
    });
  });
</script>
```

---

## 🔧 Use Cases

* 🗳 Election & polling center mapping
* 📋 Address validation and forms
* 🧭 Logistics and delivery systems
* 📊 Dashboards and geodata visualization
* 📱 Location-aware apps (e.g. census, healthcare)

---

## 📜 License

* **Data**: Licensed under the [Open Data Commons Attribution License v1.0](https://opendatacommons.org/licenses/by/1-0/)
* **Code**: Licensed under the [MIT License](LICENSE-MIT.txt)

You are free to **use, modify, and distribute** this data **with attribution**.

---

## 🤝 Contributing

Contributions are welcome!

1. Fork this repository
2. Create a new branch
3. Commit your changes
4. Open a Pull Request

---

✅ Let me know if:
- You want the GitHub username or links filled in.
- You’d like the optional `scripts/flatten.js` to convert your JSON to flat CSV.
- You’d like a `CONTRIBUTING.md` template.

All free to add!
```
