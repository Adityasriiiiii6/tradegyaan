# tradegyaan
git init
git remote add origin https://github.com/your-username/tradegyaan-website.git
import React from "react";
import { Button } from "@/components/ui/button";
import { Card, CardContent } from "@/components/ui/card";
import { motion } from "framer-motion";

export default function Home() {
  return (
    <div className="min-h-screen bg-gray-100 text-gray-900">
      <header className="bg-white shadow-md p-6 flex justify-between items-center">
        <h1 className="text-2xl font-bold text-blue-600">TradeGyaan</h1>
        <Button className="bg-blue-600 text-white px-4 py-2 rounded-xl shadow">Get Funded</Button>
      </header>

      <section className="px-8 py-16 text-center">
        <motion.h2 
          className="text-4xl font-bold mb-4"
          initial={{ opacity: 0, y: 20 }} 
          animate={{ opacity: 1, y: 0 }} 
          transition={{ duration: 0.6 }}
        >
          India’s Smartest Prop Trading Firm
        </motion.h2>
        <p className="text-lg text-gray-700 mb-8">
          Trade in our capital, keep up to 90% of the profits. No risk, only reward.
        </p>
        <Button className="bg-green-600 text-white px-6 py-3 text-lg rounded-xl">Start Evaluation</Button>
      </section>

      <section className="px-8 py-12 bg-white grid grid-cols-1 md:grid-cols-3 gap-6">
        {[
          { title: "Step 1", desc: "Join the Evaluation Challenge." },
          { title: "Step 2", desc: "Prove your trading skills." },
          { title: "Step 3", desc: "Get Funded & Keep Profits." },
        ].map((step, index) => (
          <Card key={index} className="rounded-2xl shadow-md p-6">
            <CardContent>
              <h3 className="text-xl font-semibold mb-2">{step.title}</h3>
              <p className="text-gray-600">{step.desc}</p>
            </CardContent>
          </Card>
        ))}
      </section>

      {/* Evaluation Plans Section */}
      <section className="px-8 py-16 bg-gray-50">
        <h2 className="text-3xl font-bold text-center mb-10">Choose Your Evaluation Plan</h2>
        <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
          {[
            { title: "₹10K Account", price: "₹1,199", profit: "Target: ₹1,000", refund: true },
            { title: "₹25K Account", price: "₹2,499", profit: "Target: ₹2,500", refund: true },
            { title: "₹50K Account", price: "₹4,499", profit: "Target: ₹5,000", refund: true },
          ].map((plan, index) => (
            <Card key={index} className="rounded-2xl p-6 shadow-lg">
              <CardContent className="space-y-4">
                <h3 className="text-xl font-bold">{plan.title}</h3>
                <p className="text-gray-700">{plan.profit}</p>
                <p className="text-green-600 font-semibold">{plan.price}</p>
                {plan.refund && <p className="text-sm text-gray-500">Refundable on funding</p>}
                <Button className="bg-blue-600 text-white w-full">Start Now</Button>
              </CardContent>
            </Card>
          ))}
        </div>
      </section>

      {/* Dashboard Preview Section */}
      <section className="px-8 py-16">
        <h2 className="text-3xl font-bold text-center mb-10">Dashboard Preview</h2>
        <div className="bg-white rounded-2xl shadow-md p-8 max-w-4xl mx-auto space-y-6">
          <div className="flex justify-between">
            <div>
              <p className="text-sm text-gray-500">Account</p>
              <p className="text-lg font-semibold">₹50K Evaluation</p>
            </div>
            <div>
              <p className="text-sm text-gray-500">Status</p>
              <p className="text-green-600 font-semibold">Active</p>
            </div>
          </div>
          <div className="grid grid-cols-1 md:grid-cols-3 gap-6 text-center">
            <div>
              <p className="text-sm text-gray-500">Current Balance</p>
              <p className="text-xl font-bold">₹52,100</p>
            </div>
            <div>
              <p className="text-sm text-gray-500">Daily Drawdown</p>
              <p className="text-xl font-bold text-red-500">₹1,500</p>
            </div>
            <div>
              <p className="text-sm text-gray-500">Profit Target</p>
              <p className="text-xl font-bold">₹5,000</p>
            </div>
          </div>
          <Button className="w-full bg-blue-600 text-white">Go to Full Dashboard</Button>
        </div>
      </section>

      <footer className="p-6 text-center text-gray-600 text-sm">
        © 2025 TradeGyaan. All rights reserved.
      </footer>
    </div>
  );
}
