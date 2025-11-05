# team-project
gender responsive mechanism to combat domestic violence
import React, { useState } from "react";
import { motion } from "framer-motion";

// Gender-Responsive Mechanisms - English only
// Single-file React component for a public-facing website
// - Assumes Tailwind CSS is configured in the project
// - Install framer-motion: npm i framer-motion

export default function GenderResponsiveDVWebsite() {
  const [form, setForm] = useState({ name: "", email: "", message: "" });
  const [submitted, setSubmitted] = useState(false);

  const mechanisms = [
    {
      title: "Legal Strengthening",
      desc: "Improve legal frameworks, streamline protection orders, and strengthen enforcement to ensure survivor safety.",
    },
    {
      title: "Survivor-Centered Services",
      desc: "Provide trauma-informed counselling, shelters, and economic support tailored to survivors' needs.",
    },
    {
      title: "Multi-Agency Coordination",
      desc: "Create coordinated referral pathways across health, police, legal and social services.",
    },
    {
      title: "Gender-Sensitive Training",
      desc: "Train frontline workers (police, health professionals) in gender sensitivity and survivor rights.",
    },
    {
      title: "Community Engagement",
      desc: "Engage men, youth and community leaders in prevention, not just response.",
    },
  ];

  function handleChange(e) {
    setForm({ ...form, [e.target.name]: e.target.value });
  }

  function handleSubmit(e) {
    e.preventDefault();
    // Note: this example does NOT send data to a server. Plug in your API endpoint in production.
    setSubmitted(true);
    setForm({ name: "", email: "", message: "" });
    setTimeout(() => setSubmitted(false), 4000);
  }

  return (
    <div className="min-h-screen bg-gray-50 text-gray-900 antialiased">
      <header className="bg-gradient-to-r from-indigo-600 to-teal-500 text-white">
        <div className="max-w-6xl mx-auto px-6 py-6 flex items-center justify-between">
          <div className="flex items-center gap-4">
            <div className="w-12 h-12 rounded-lg bg-white/20 flex items-center justify-center font-bold">GR</div>
            <div>
              <h1 className="text-xl font-semibold">Gender-Responsive Mechanisms</h1>
              <p className="text-sm opacity-90">Combating Domestic Violence — Survivor-centered, systemic, community-based</p>
            </div>
          </div>

          <nav className="flex items-center gap-4">
            <a href="#resources" className="text-sm opacity-90 hover:underline">Resources</a>
            <a href="#contact" className="text-sm bg-white/20 px-3 py-1 rounded-md">Contact</a>
          </nav>
        </div>
      </header>

      <main className="max-w-6xl mx-auto px-6 py-12">
        <section className="grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
          <motion.div initial={{ opacity: 0, y: 10 }} animate={{ opacity: 1, y: 0 }} transition={{ duration: 0.5 }}>
            <h2 className="text-3xl font-extrabold mb-4">A practical framework to prevent, protect and respond</h2>
            <p className="mb-6 text-gray-700">Domestic violence requires coordinated legal, social and community action. This site outlines gender-responsive mechanisms that prioritize survivors' safety and long-term recovery.</p>

            <div className="flex gap-3">
              <a href="#contact" className="px-4 py-2 bg-indigo-600 text-white rounded-md shadow hover:brightness-95">Get Help</a>
              <a href="#resources" className="px-4 py-2 border border-indigo-200 rounded-md">Learn More</a>
            </div>
          </motion.div>

          <motion.div initial={{ opacity: 0, scale: 0.98 }} animate={{ opacity: 1, scale: 1 }} transition={{ duration: 0.5 }} className="bg-white p-6 rounded-2xl shadow">
            <h3 className="font-semibold text-lg mb-3">Quick Actions</h3>
            <ul className="space-y-3 text-sm">
              <li className="flex items-start gap-3">
                <div className="w-10 h-10 rounded-md bg-indigo-50 flex items-center justify-center">📞</div>
                <div>
                  <div className="font-medium">Emergency Hotline</div>
                  <div className="text-gray-600 text-sm">Call local emergency number or child protection hotline depending on your country.</div>
                </div>
              </li>

              <li className="flex items-start gap-3">
                <div className="w-10 h-10 rounded-md bg-indigo-50 flex items-center justify-center">🏠</div>
                <div>
                  <div className="font-medium">Shelters & Safe Housing</div>
                  <div className="text-gray-600 text-sm">Find immediate safe accommodation through local NGOs and government programs.</div>
                </div>
              </li>

              <li className="flex items-start gap-3">
                <div className="w-10 h-10 rounded-md bg-indigo-50 flex items-center justify-center">⚖️</div>
                <div>
                  <div className="font-medium">Protection Orders</div>
                  <div className="text-gray-600 text-sm">Legal options to restrict abusers and secure survivor safety.</div>
                </div>
              </li>
            </ul>
          </motion.div>
        </section>

        <section className="mt-12">
          <h3 className="text-2xl font-bold mb-6">Core Gender-Responsive Mechanisms</h3>

          <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
            {mechanisms.map((m, i) => (
              <motion.article key={i} className="bg-white p-5 rounded-xl shadow hover:shadow-lg" whileHover={{ y: -4 }}>
                <h4 className="font-semibold mb-2">{m.title}</h4>
                <p className="text-sm text-gray-700">{m.desc}</p>
              </motion.article>
            ))}
          </div>
        </section>

        <section id="resources" className="mt-12">
          <div className="flex items-start justify-between gap-6">
            <div className="flex-1">
              <h3 className="text-2xl font-bold">Resources & Toolkits</h3>
              <p className="text-gray-600 mt-2">Practical guides, legal checklists, and referral maps for organizations and survivors.</p>

              <ul className="mt-4 space-y-2 text-sm">
                <li className="flex items-center gap-3">
                  <div className="w-8 h-8 rounded bg-indigo-100 flex items-center justify-center">📄</div>
                  <a href="#" className="underline">Survivor Safety Checklist (PDF)</a>
                </li>
                <li className="flex items-center gap-3">
                  <div className="w-8 h-8 rounded bg-indigo-100 flex items-center justify-center">🗺️</div>
                  <a href="#" className="underline">Local Referral Map</a>
                </li>
                <li className="flex items-center gap-3">
                  <div className="w-8 h-8 rounded bg-indigo-100 flex items-center justify-center">🎥</div>
                  <a href="#" className="underline">Training Slides for Frontline Workers</a>
                </li>
              </ul>
            </div>

            <aside className="w-72 bg-white p-4 rounded-xl shadow flex-shrink-0">
              <h4 className="font-semibold mb-2">Policy Brief</h4>
              <p className="text-sm text-gray-600 mb-3">Short brief summarizing recommended system reforms for policy makers.</p>
              <a href="#" className="block text-center px-3 py-2 bg-teal-600 text-white rounded-md">Download PDF</a>
            </aside>
          </div>
        </section>

        <section id="contact" className="mt-12 bg-white p-6 rounded-xl shadow">
          <h3 className="text-xl font-bold mb-4">Contact & Support</h3>

          <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
            <div>
              <p className="text-gray-700 mb-4">If you are a survivor, service provider, or policymaker and want to connect, use the form or the hotline details here.</p>

              <div className="space-y-3 text-sm">
                <div>
                  <div className="font-medium">Hotline:</div>
                  <div className="text-gray-600">+91 112 233 4455</div>
                </div>
                <div>
                  <div className="font-medium">Email:</div>
                  <div className="text-gray-600">help@example.org</div>
                </div>
                <div>
                  <div className="font-medium">Address:</div>
                  <div className="text-gray-600">123 Safety Lane, Your City</div>
                </div>
              </div>
            </div>

            <form onSubmit={handleSubmit} className="space-y-3">
              <div>
                <label className="text-sm">Name</label>
                <input name="name" value={form.name} onChange={handleChange} className="mt-1 block w-full rounded-md border-gray-200 shadow-sm p-2" />
              </div>
              <div>
                <label className="text-sm">Email</label>
                <input name="email" value={form.email} onChange={handleChange} className="mt-1 block w-full rounded-md border-gray-200 shadow-sm p-2" />
              </div>
              <div>
                <label className="text-sm">Message</label>
                <textarea name="message" value={form.message} onChange={handleChange} className="mt-1 block w-full rounded-md border-gray-200 shadow-sm p-2 h-24" />
              </div>
              <div className="flex gap-3">
                <button type="submit" className="px-4 py-2 bg-indigo-600 text-white rounded-md">Send</button>
                <button type="button" onClick={() => setForm({ name: "", email: "", message: "" })} className="px-4 py-2 border rounded-md">Reset</button>
              </div>

              {submitted && <div className="mt-2 text-sm text-teal-700">Thanks — we'll get back to you if you requested follow-up.</div>}
            </form>
          </div>
        </section>

        <section className="mt-12 text-sm text-gray-600">
          <h4 className="font-semibold">Guiding Principles</h4>
          <ul className="mt-2 list-disc list-inside">
            <li>Survivor safety and agency prioritized.</li>
            <li>Intersectional approaches that recognize diverse barriers.</li>
            <li>Evidence-based policy and monitoring.</li>
            <li>Community-led prevention and accountability.</li>
          </ul>
        </section>
      </main>

      <footer className="bg-white border-t mt-12">
        <div className="max-w-6xl mx-auto px-6 py-6 flex flex-col md:flex-row items-center justify-between gap-4">
          <div className="text-sm text-gray-600">© {new Date().getFullYear()} Gender-Responsive Mechanisms • All rights reserved</div>
          <div className="flex items-center gap-3 text-sm">
            <a href="#" className="underline">Privacy</a>
            <a href="#" className="underline">Terms</a>
            <a href="#" className="underline">Report an issue</a>
          </div>
        </div>
      </footer>
    </div>
  );
}
