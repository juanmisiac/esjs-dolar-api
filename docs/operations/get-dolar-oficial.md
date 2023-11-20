---
aside: false
outline: false
title: Dólar Oficial
---

<script setup>
import { useRoute } from 'vitepress'
import Operation from '@theme/components/Operation.vue'
import OperationEndpoint from '@theme/components/OperationEndpoint.vue'
import Responses from '@theme/components/Responses.vue'
import ResponseBody from '@theme/components/ResponseBody.vue'
import TryItButton from '@theme/components/TryItButton.vue'
</script>

<Operation method="GET" id="get-dolar-oficial">

<template #header="header">

# Dólar Oficial

</template>

<template #description="description">

<OperationEndpoint :method="description.method" :path="description.path" :baseUrl="description.baseUrl" />



<!--@include: ./parts/get-dolar-oficial-description-after.md -->

</template>

<template #responses="responses">

## {{ $t('Response') }}

<Responses :responses="responses.responses" :schema="responses.schema" :responseType="responses.responseType">

<template #body="body">

<ResponseBody :schema="body.schema" :responseType="body.responseType" />

</template>

<template #example="example">

```json
{
  "compra": "number",
  "venta": "number",
  "casa": "string",
  "nombre": "string",
  "moneda": "string",
  "fechaActualizacion": "string"
}
```

</template>

</Responses>

</template>

<template #try-it="tryIt">

<TryItButton :operation-id="tryIt.operationId" :method="tryIt.method">

<template #response="response">

```json-vue
{{ response.response }}
```

</template>

</TryItButton>

</template>

<template #samples="samples">

## {{ $t('Samples') }}

::: code-group

```bash [cURL] 
curl -X GET https://dolarapi.com/v1/dolares/oficial
```

```js-vue [JavaScript]
fetch("https://dolarapi.com/v1/dolares/oficial")
  .then(response => response.json())
  .then(data => console.log(data));
```

```php-vue [PHP]
file_get_contents("https://dolarapi.com/v1/dolares/oficial")
```

```python-vue [Python]
import requests
response = requests.get("https://dolarapi.com/v1/dolares/oficial")
print(response.json())
```

:::

</template>

</Operation>