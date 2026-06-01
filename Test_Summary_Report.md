# Test Summary Report – Swiggy Manual Testing

**Project:** Swiggy Food Delivery App – Manual Testing  
**Tester:** Raghav Gaur  
**Test Period:** May 2026  
**Platform:** Android App + Chrome Web  

---

## 1. Objective

To validate the functional correctness and user experience quality of Swiggy's core flows — Login, Search, Cart, and Checkout — through structured manual testing.

---

## 2. Test Environment

| Parameter | Details |
|---|---|
| Device | Android (OnePlus/Samsung mid-range) |
| Browser | Google Chrome |
| Network | 5G mobile data + WiFi |
| App Version | Swiggy Android v4.x |
| OS | Android 12 |

---

## 3. Modules Tested

### 3.1 Login & Authentication
- Valid mobile number + correct OTP → **Pass**
- Invalid mobile number (less than 10 digits) → **Pass** (error shown correctly)
- Expired OTP entry → **Pass** (error handled)
- OTP resend before timer → **Fail** – BUG-003 raised
- Session persistence after app backgrounded → **Pass**

### 3.2 Search & Restaurant Discovery
- Search by exact restaurant name → **Pass**
- Search by partial name (3 characters) → **Fail** – BUG-002 raised
- Search with cuisine keyword (e.g. "biryani") → **Pass**
- Filter by "Pure Veg" → **Pass**
- Filter by rating (4.0+) → **Pass**
- Search with empty input → **Pass** (no crash, shows trending)

### 3.3 Cart Management
- Add single item to cart → **Pass**
- Add multiple items from same restaurant → **Pass**
- Increase item quantity → **Fail** – BUG-001 raised (price not updated)
- Remove item (Android) → **Fail** – BUG-005 raised
- Add items from two different restaurants → **Pass** (conflict prompt shown)
- Cart persistence after app close and reopen → **Pass**

### 3.4 Checkout & Address
- Proceed to checkout with valid cart → **Pass**
- Apply valid coupon code → **Pass**
- Apply invalid coupon, then valid coupon → **Fail** – BUG-004 raised
- Select saved address → **Pass**
- Enter new address with special characters → **Fail** – BUG-006 raised (crash)
- Navigate to payment screen → **Blocked** (could not proceed due to BUG-006 in prior step)

---

## 4. Defect Summary

| Severity | Count |
|---|---|
| High | 3 |
| Medium | 2 |
| Low | 1 |
| **Total** | **6** |

---

## 5. Observations & Recommendations

- **Cart price sync** is a critical issue — users may be misled about total before payment. Recommend immediate fix.
- **Address field crash** on special characters is a High severity bug likely caused by missing input sanitisation. Needs fix before production.
- **OTP resend timer bypass** is a security concern — could be exploited for OTP flooding.
- Search partial-match improvement would significantly improve discovery experience for Tier-2 users who may mistype restaurant names.

---

## 6. Conclusion

Core flows of Swiggy are largely functional. However, 3 High severity bugs were identified that directly impact user trust and conversion — particularly the cart pricing bug and address field crash. These should be prioritised in the next sprint.
