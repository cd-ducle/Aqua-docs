# Aqua's query language

Aqua's query language document

## Usage

### Filter simple properties
```json
{
    "id": "entity_1",
    "details":{
        "age": 18,
        "gender": "female",
    },
    "name": "Aqua",
    "attributeValues": [
        {
          "id": 1,
          "entityId": "entity_1",
          "attributeCode": "hair_color",
          "value": "blue"
        }
    ]
}
```

```
filter[<field_name_1>][<field_name_1.1>]...[<field_name_1.1...n>][<operator>] = <value>
```
Example 
```
filter[id][eq] = entity_1
filter[details][age][eq] = 18
```
### Filter attributes (EAV)
```
eavFilter[<attribute_code>][<operator>] = <value>
```
Example 
```
eavFilter[hair_color][eq] = blue
```

### Sort by simple properties
```
sort[<field_name>] = desc | asc
```
Example 
```
sort[createdAt] = desc
```
## Operators

| Operator    | Description |
| ----------- | ----------- |
| [eq](#eq)| Equal|
| [not](#not)| Not|
| [gt](#gt)| Greater than|
| [lt](#lt)| Less than|
| [gte](#gte)| Greater than or equal|
| [lte](#lte)| Less than or equal|
| [in](#in) | In|
| [notIn](#notIn)| Not in|
| [contains](#contains)| Contains character string|
| [startWith](#startWith)| Start with character string|
| [endWith](#endWith)| End with character string|
| [isNull](#isNull)| Is null|
| [isNotNull](#isNotNull)| Is not null|
| [isTrue](#isTrue)| Equal true|
| [isFalse](#isFalse)| Equal false|

## Details
### eq

```
filter[gender][eq]=female
```

Tìm tất cả dữ liệu có *gender* `bằng` *female*

*Note: Không dùng với giá trị null hoặc boolean*

---

### not

```
filter[gender][not]=male
```

Tìm tất cả dữ liệu có *gender* `không bằng` *male*

*Note: Không dùng với giá trị null hoặc boolean*

---

### gt

```
filter[price][gt]=6900
```

Tìm tất cả dữ liệu có *price* `lớn hơn` *6900*

---

### lt

```
filter[price][lt]=9600
```

Tìm tất cả dữ liệu có *price* `nhỏ hơn` *9600*

---

### gte

```
filter[age][gte]=18
```

Tìm tất cả dữ liệu có *age* `lớn hơn hoặc bằng` *18*

---

### lte

```
filter[age][lte]=23
```

Tìm tất cả dữ liệu có *age* `nhỏ hơn hoặc bằng` *23*

---

### in

```
filter[color][in]=red
filter[color][in]=blue
```

Tìm tất cả dữ liệu có *color* `bằng` *red* `hoặc bằng` *blue*

---

### notIn

```
filter[color][in]=red
filter[color][in]=blue
```

Tìm tất cả dữ liệu có *color* `không bằng` *red* `và không bằng` *blue*

---

### contains

```
filter[fullName][contains]=Trọng Anh
```

Tìm tất cả dữ liệu có *fullName* `chứa chuỗi` *Trọng Anh*

---

### startWith

```
filter[fullName][startWith]=Lê
```

---

Tìm tất cả dữ liệu có *fullName* `bắt đầu bằng chuỗi` *Lê*

### endWith

```
filter[fullName][endWith]=Đức
```

Tìm tất cả dữ liệu có *fullName* `kết thúc bằng chuỗi` *Đức*

---

### isNull

```
filter[description][isNull] // Không cần truyền giá trị hoặc có thể truyền bất cứ giá trị nào
```

Tìm tất cả dữ liệu có *description* `bằng` *null*

---

### isNotNull

```
filter[description][isNotNull] // Không cần truyền giá trị hoặc có thể truyền bất cứ giá trị nào
```

Tìm tất cả dữ liệu có *description* `không` *null*

---

### isTrue

```
filter[checked][isTrue] // Không cần truyền giá trị hoặc có thể truyền bất cứ giá trị nào
```

Tìm tất cả dữ liệu có *checked* `bằng` *true*

---

### isFalse

```
filter[checked][isFalse] // Không cần truyền giá trị hoặc có thể truyền bất cứ giá trị nào
```

Tìm tất cả dữ liệu có *checked* `bằng` *false*

---
