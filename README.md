# emergency-tree-service-md
/emergencytreeservicemd
├─ pages/
│  ├─ index.js         // Homepage
│  ├─ emergency.js     // Emergency Tree Removal page
│  ├─ services.js      // Tree Removal Services page
│  ├─ areas.js         // Service Areas page
│  ├─ contact.js       // Contact page
├─ components/
│  ├─ Header.js
│  ├─ Footer.js
│  ├─ CTAButton.js
│  ├─ ServiceCard.js
├─ public/
│  └─ images/          // Optional stock/tree images
├─ styles/
│  └─ globals.css
import Link from "next/link";

export default function Header() {
  return (
    <header className="bg-green-700 text-white p-4 flex justify-between items-center">
      <h1 className="font-bold text-xl">Emergency Tree Service MD</h1>
      <nav className="space-x-4">
        <Link href="/">Home</Link>
        <Link href="/emergency">Emergency</Link>
        <Link href="/services">Services</Link>
        <Link href="/areas">Areas</Link>
        <Link href="/contact">Contact</Link>
      </nav>
      <a href="tel:3015551234" className="bg-yellow-500 text-black px-3 py-1 rounded">Call Now</a>
    </header>
  );
}export default function CTAButton({ text, phone }) {
  return (
    <a href={`tel:${phone}`} className="bg-yellow-500 text-black px-6 py-3 rounded font-bold inline-block mt-4">
      {text}
    </a>
  );
}import Header from "../components/Header";
import CTAButton from "../components/CTAButton";
import Footer from "../components/Footer";

export default function Home() {
  return (
    <>
      <Header />
      <main className="p-8 text-center">
        <h1 className="text-4xl font-bold mb-4">Emergency Tree Removal in Montgomery County, MD</h1>
        <p className="mb-6">Fast, reliable tree removal when storms strike. 24/7 service across Montgomery County.</p>
        <CTAButton text="Call Now" phone="3015551234" />

        <section className="mt-12">
          <h2 className="text-2xl font-semibold mb-4">Our Services</h2>
          <ul className="space-y-2">
            <li><a href="/emergency">Emergency Tree Removal</a></li>
            <li>Tree Cutting & Trimming</li>
            <li>Stump Grinding</li>
            <li>Hazardous Tree Removal</li>
          </ul>
        </section>

        <section className="mt-12">
          <h2 className="text-2xl font-semibold mb-4">Service Areas</h2>
          <p>Rockville, Bethesda, Silver Spring, Gaithersburg, Germantown, Wheaton, Potomac, Chevy Chase</p>
        </section>
      </main>
      <Footer />
    </>
  );
}import Header from "../components/Header";
import Footer from "../components/Footer";
import CTAButton from "../components/CTAButton";

export default function Emergency() {
  return (
    <>
      <Header />
      <main className="p-8">
        <h1 className="text-4xl font-bold mb-4">24/7 Emergency Tree Removal in Montgomery County, MD</h1>
        <p className="mb-4">
          Storm damage, fallen trees, and dangerous limbs can’t wait. Our emergency tree service responds immediately to protect your home and property.
        </p>
        <ul className="list-disc ml-8 mb-4">
          <li>Trees fallen on homes or cars</li>
          <li>Storm-damaged trees</li>
          <li>Split or leaning trees</li>
          <li>Blocked driveways or roads</li>
          <li>Insurance-related tree removal</li>
        </ul>
        <CTAButton text="Call Now for Immediate Service" phone="3015551234" />
      </main>
      <Footer />
    </>
  );
}import Header from "../components/Header";
import Footer from "../components/Footer";
import ServiceCard from "../components/ServiceCard";

export default function Services() {
  const services = [
    "Emergency Tree Removal",
    "Tree Cutting & Trimming",
    "Stump Grinding",
    "Hazardous Tree Removal"
  ];

  return (
    <>
      <Header />
      <main className="p-8">
        <h1 className="text-4xl font-bold mb-6">Tree Removal Services</h1>
        <div className="grid gap-6">
          {services.map(service => (
            <ServiceCard key={service} title={service} />
          ))}
        </div>
      </main>
      <Footer />
    </>
  );
}export default function ServiceCard({ title }) {
  return (
    <div className="border p-4 rounded shadow hover:shadow-lg transition">
      <h3 className="font-bold text-xl mb-2">{title}</h3>
      <p>Professional {title.toLowerCase()} for Montgomery County homeowners and businesses.</p>
    </div>
  );
}import Header from "../components/Header";
import Footer from "../components/Footer";

export default function Areas() {
  const cities = ["Rockville", "Bethesda", "Silver Spring", "Gaithersburg", "Germantown", "Wheaton", "Potomac", "Chevy Chase"];

  return (
    <>
      <Header />
      <main className="p-8">
        <h1 className="text-4xl font-bold mb-4">Service Areas</h1>
        <p className="mb-6">We proudly serve Montgomery County, MD, including:</p>
        <ul className="list-disc ml-8 space-y-2">
          {cities.map(city => <li key={city}>{city}: Emergency tree removal and storm cleanup services</li>)}
        </ul>
      </main>
      <Footer />
    </>
  );
}import Header from "../components/Header";
import Footer from "../components/Footer";

export default function Contact() {
  return (
    <>
      <Header />
      <main className="p-8 max-w-xl mx-auto">
        <h1 className="text-4xl font-bold mb-4">Contact Us</h1>
        <p className="mb-4">Emergency calls answered 24/7. Call or fill out the form below.</p>
        <a href="tel:3015551234" className="bg-yellow-500 text-black px-6 py-3 rounded font-bold inline-block mb-6">Call Now</a>
        <form className="flex flex-col space-y-4">
          <input type="text" placeholder="Name" className="border p-2 rounded" />
          <input type="tel" placeholder="Phone" className="border p-2 rounded" />
          <textarea placeholder="Message" className="border p-2 rounded"></textarea>
          <button type="submit" className="bg-green-700 text-white px-4 py-2 rounded font-bold">Submit</button>
        </form>
      </main>
      <Footer />
    </>
  );
}export default function Footer() {
  return (
    <footer className="bg-green-700 text-white p-4 mt-12 text-center">
      © {new Date().getFullYear()} Emergency Tree Service MD. All rights reserved.
    </footer>
  );
}
