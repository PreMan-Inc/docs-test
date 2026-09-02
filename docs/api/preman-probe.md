# preman_probe

Base URL: `https://xixoo2yundjxsbdwl3iw2eg5hi0ckwfu.lambda-url.us-east-1.on.aws`

## Get a discount

`GET /api/v1/preman-probe/discount`

Returns discount information from the Preman probe.

**Query parameters**

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| `percent_off` | integer | no | — |

**Responses**

| Status | Description | Type |
| --- | --- | --- |
| `200` | Successful response | PremanProbeDiscountApiV1PremanProbeDiscountGetResponse |
| `422` | Unprocessable entity | any |

**Example response**

```json
{
  "order_id": "string",
  "percent_off": 0,
  "total": 0.0
}
```

**Example request**

```bash
curl -X GET 'https://xixoo2yundjxsbdwl3iw2eg5hi0ckwfu.lambda-url.us-east-1.on.aws/api/v1/preman-probe/discount'
```

---

## Get an order total

`GET /api/v1/preman-probe/order-total`

Returns order total information from the Preman probe.

**Responses**

| Status | Description | Type |
| --- | --- | --- |
| `200` | Successful response | PremanProbeOrderTotalApiV1PremanProbeOrderTotalGetResponse |

**Example response**

```json
{
  "currency": "string",
  "order_id": "string",
  "paid": true,
  "total": 0.0
}
```

**Example request**

```bash
curl -X GET 'https://xixoo2yundjxsbdwl3iw2eg5hi0ckwfu.lambda-url.us-east-1.on.aws/api/v1/preman-probe/order-total'
```

---

## Get a refund status

`GET /api/v1/preman-probe/refund-status`

Returns refund status information from the Preman probe.

**Responses**

| Status | Description | Type |
| --- | --- | --- |
| `200` | Successful response | PremanProbeRefundStatusApiV1PremanProbeRefundStatusGetResponse |

**Example response**

```json
{
  "amount_refunded": 0.0,
  "currency": "GBP",
  "order_id": "string",
  "refunded_at": "string",
  "state": "string"
}
```

**Example request**

```bash
curl -X GET 'https://xixoo2yundjxsbdwl3iw2eg5hi0ckwfu.lambda-url.us-east-1.on.aws/api/v1/preman-probe/refund-status'
```

---

## Get a shipping estimate

`GET /api/v1/preman-probe/shipping-estimate`

Returns shipping estimate information from the Preman probe.

**Responses**

| Status | Description | Type |
| --- | --- | --- |
| `200` | Successful response | PremanProbeShippingEstimateApiV1PremanProbeShippingEstimateGetResponse |

**Example response**

```json
{
  "business_days": 0,
  "carrier": "string",
  "order_id": "string"
}
```

**Example request**

```bash
curl -X GET 'https://xixoo2yundjxsbdwl3iw2eg5hi0ckwfu.lambda-url.us-east-1.on.aws/api/v1/preman-probe/shipping-estimate'
```

---
