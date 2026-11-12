# MATRA VASTRA — Netlify project

Static 3D site + Netlify Functions for Razorpay (test mode first).

## Environment variables (Netlify → Site configuration → Environment variables)
- RAZORPAY_KEY_ID      = rzp_test_xxxxxxxx   (test key)
- RAZORPAY_KEY_SECRET  = your test key secret  (never put it in code or chat)
- ADMIN_KEY            = any long private password (for the owner order panel)

## Owner: see orders / update status
List:   curl -H "x-admin-key: YOUR_ADMIN_KEY" https://thematravastra.in/api/admin
Update: curl -X POST -H "x-admin-key: YOUR_ADMIN_KEY" -H "Content-Type: application/json" \
        -d '{"ref":"MVXXXX","status":"Shipped"}' https://thematravastra.in/api/admin

## Edit products
public/products.json (id, name, collection, price, desc). Prices are enforced on the server.
Photos: see public/assets/README.txt

## Go live with real payments
After Razorpay KYC: replace the test key pair with the Live key pair in Netlify env vars, then redeploy.
