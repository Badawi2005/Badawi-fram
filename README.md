import { motion } from "framer-motion";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { ShoppingCart, Truck, ShieldCheck, Phone } from "lucide-react";

export default function BadawiFramTelurShop() {
  return (
    <div className="min-h-screen bg-gradient-to-b from-yellow-50 to-orange-100 text-slate-800">
      {/* HERO */}
      <section className="py-20 px-6 text-center">
        <motion.h1
          initial={{ opacity: 0, y: 20 }}
          animate={{ opacity: 1, y: 0 }}
          className="text-4xl md:text-5xl font-bold mb-4"
        >
          BADAWI FRAM EGG STORE
        </motion.h1>
        <p className="text-lg text-slate-600 max-w-xl mx-auto mb-6">
          Penjualan telur ayam segar – grosir & eceran. Langsung dari peternak, harga jujur.
        </p>
        <Button className="rounded-2xl px-8 py-5 text-lg">
          <ShoppingCart className="mr-2" /> Pesan via WhatsApp
        </Button>
      </section>

      {/* PRODUK */}
      <section className="px-6 pb-16">
        <h2 className="text-3xl font-semibold text-center mb-10">Produk Kami</h2>
        <div className="grid md:grid-cols-3 gap-6 max-w-6xl mx-auto">
          <Product name="Telur eceran" price="Rp 27.000 / kg" desc="Segar setiap hari" />
          
          <Product name="Telur Grosir" price="Rp 25.800 / kg" desc="Untuk warung & UMKM" />
        </div>
      </section>

      {/* KEUNGGULAN */}
      <section className="bg-white py-16 px-6">
        <div className="grid md:grid-cols-4 gap-6 max-w-6xl mx-auto text-center">
          <Benefit icon={<Truck />} title="Pengiriman Cepat" desc="Area lokal & sekitar" />
          <Benefit icon={<ShieldCheck />} title="Kualitas Terjamin" desc="Sortir & bersih" />
          <Benefit icon={<ShoppingCart />} title="Harga Stabil" desc="Langsung peternak" />
          <Benefit icon={<Phone />} title="Mudah Order" desc="WA & Online" />
        </div>
      </section>

      {/* CTA */}
      <section className="py-16 text-center">
        <h2 className="text-2xl font-semibold mb-4">Siap Order Telur Hari Ini?</h2>
        <p className="text-slate-600 mb-2">Order langsung via WhatsApp (tanpa ongkir per wilayah).</p>
        <p className="text-slate-600 mb-6">Pembayaran: Crypto • DANA • ShopeePay</p>
        <Button className="rounded-2xl px-8 py-5 text-lg">Order via WhatsApp</Button>
      </section>

      {/* FOOTER */}
      <footer className="text-center py-6 text-slate-500 text-sm">
        © {new Date().getFullYear()} BADAWI FRAM – Penjualan Telur Segar
      </footer>
    </div>
  );
}

function Product({ name, price, desc }) {
  return (
    <Card className="rounded-2xl shadow-md">
      <CardContent className="p-6 text-center">
        <h3 className="text-xl font-semibold mb-2">{name}</h3>
        <p className="text-slate-500 mb-2">{desc}</p>
        <p className="font-bold text-lg mb-4">{price}</p>
        <Button className="rounded-xl w-full">Tambah ke Keranjang</Button>
      </CardContent>
    </Card>
  );
}

// Benefit section
function Benefit({ icon, title, desc }) {
  return (
    <div>
      <div className="flex justify-center mb-3 text-orange-500">{icon}</div>
      <h4 className="font-semibold mb-1">{title}</h4>
      <p className="text-slate-500 text-sm">{desc}</p>
    </div>
  );
}
