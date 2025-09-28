#"use client";

import { useState } from "react";
import { Button } from "@/components/ui/button";
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";
import { Input } from "@/components/ui/input";
import { Label } from "@/components/ui/label";
import {
  Menu,
  X,
  Play,
  Star,
  Check,
  ChevronRight,
  Award,
  Users,
  Clock,
  Heart,
  ArrowRight,
  Calendar,
  TrendingUp,
  Target,
  BarChart3,
} from "lucide-react";

export default function FitnessLandingPage() {
  const [isMenuOpen, setIsMenuOpen] = useState(false);
  const [activeTab, setActiveTab] = useState("monthly");

  const subscriptionPlans = [
    {
      name: "Starter",
      price: { monthly: "$29", yearly: "$249" },
      description: "Perfect for beginners starting their fitness journey",
      features: [
        "Access to basic workout library",
        "5 new workouts per month",
        "Basic nutrition guide",
        "Email support",
        "Progress tracking",
      ],
      popular: false,
    },
    {
      name: "Pro",
      price: { monthly: "$59", yearly: "$499" },
      description: "Ideal for regular exercisers seeking variety",
      features: [
        "Full workout library access",
        "15 new workouts per month",
        "Advanced nutrition plans",
        "Priority support",
        "Advanced progress tracking",
        "Custom workout plans",
        "1 live class per week",
      ],
      popular: true,
    },
    {
      name: "Elite",
      price: { monthly: "$99", yearly: "$899" },
      description: "For fitness enthusiasts who want it all",
      features: [
        "All Pro features plus:",
        "Unlimited new workouts",
        "Personalized coaching",
        "24/7 support",
        "All live classes",
        "1-on-1 sessions monthly",
        "Recovery techniques",
        "Exclusive community",
      ],
      popular: false,
    },
  ];

  const trainers = [
    {
      name: "Sarah Johnson",
      specialty: "HIIT & Strength Training",
      experience: "8 years",
      rating: 4.9,
      clients: 1200,
    },
    {
      name: "Marcus Chen",
      specialty: "Yoga & Flexibility",
      experience: "10 years",
      rating: 4.8,
      clients: 950,
    },
    {
      name: "Jessica Williams",
      specialty: "Pilates & Core Strength",
      experience: "7 years",
      rating: 4.9,
      clients: 850,
    },
    {
      name: "David Rodriguez",
      specialty: "Cardio & Endurance",
      experience: "12 years",
      rating: 4.7,
      clients: 1500,
    },
  ];

  return (
    <main className="min-h-screen bg-background">
      {/* Header */}
      <header className="sticky top-0 z-50 border-b border-border bg-background/95 backdrop-blur supports-[backdrop-filter]:bg-background/60">
        <div className="container mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex h-16 items-center justify-between">
            {/* Logo */}
            <div className="flex items-center">
              <div className="flex-shrink-0">
                <h1 className="text-2xl font-bold text-primary">FitPro</h1>
              </div>
            </div>

            {/* Desktop Navigation */}
            <nav className="hidden md:block">
              <div className="ml-10 flex items-baseline space-x-8">
                <a
                  href="#workouts"
                  className="text-foreground transition-colors hover:text-primary"
                >
                  Workouts
                </a>
                <a
                  href="#trainers"
                  className="text-foreground transition-colors hover:text-primary"
                >
                  Trainers
                </a>
                <a
                  href="#pricing"
                  className="text-foreground transition-colors hover:text-primary"
                >
                  Pricing
                </a>
                <a
                  href="#progress"
                  className="text-foreground transition-colors hover:text-primary"
                >
                  Progress
                </a>
              </div>
            </nav>

            {/* CTA Button */}
            <div className="hidden md:block">
              <Button className="bg-primary text-primary-foreground hover:bg-primary/90">
                Start Free Trial
              </Button>
            </div>

            {/* Mobile menu button */}
            <div className="md:hidden">
              <button
                onClick={() => setIsMenuOpen(!isMenuOpen)}
                className="text-foreground hover:text-primary"
              >
                {isMenuOpen ? <X size={24} /> : <Menu size={24} />}
              </button>
            </div>
          </div>

          {/* Mobile Navigation */}
          {isMenuOpen && (
            <div className="md:hidden">
              <div className="space-y-1 border-t border-border px-2 pb-3 pt-2 sm:px-3">
                <a
                  href="#workouts"
                  className="block px-3 py-2 text-foreground hover:text-primary"
                >
                  Workouts
                </a>
                <a
                  href="#trainers"
                  className="block px-3 py-2 text-foreground hover:text-primary"
                >
                  Trainers
                </a>
                <a
                  href="#pricing"
                  className="block px-3 py-2 text-foreground hover:text-primary"
                >
                  Pricing
                </a>
                <a
                  href="#progress"
                  className="block px-3 py-2 text-foreground hover:text-primary"
                >
                  Progress
                </a>
                <div className="px-3 py-2">
                  <Button className="w-full bg-primary text-primary-foreground hover:bg-primary/90">
                    Start Free Trial
                  </Button>
                </div>
              </div>
            </div>
          )}
        </div>
      </header>

      {/* Hero Section */}
      <section className="relative overflow-hidden bg-gradient-to-br from-primary/10 to-primary/5 py-20 lg:py-32">
        <div className="container relative mx-auto px-4 sm:px-6 lg:px-8">
          <div className="mx-auto max-w-4xl text-center">
            <h1 className="mb-6 text-4xl font-black leading-tight text-foreground sm:text-5xl lg:text-6xl">
              Transform Your Body,{" "}
              <span className="text-primary">Transform Your Life</span>
            </h1>

            <p className="mx-auto mb-8 max-w-2xl text-xl leading-relaxed text-muted-foreground">
              Join thousands who have achieved their fitness goals with our
              expert-led programs, personalized training, and supportive
              community.
            </p>

            <div className="flex flex-col items-center justify-center gap-4 sm:flex-row">
              <Button
                size="lg"
                className="bg-primary px-8 py-3 text-primary-foreground hover:bg-primary/90"
              >
                Start Your Journey
                <ArrowRight className="ml-2 h-5 w-5" />
              </Button>
              <Button
                variant="outline"
                size="lg"
                className="border-primary bg-transparent px-8 py-3 text-primary hover:bg-primary hover:text-primary-foreground"
              >
                <Play className="mr-2 h-5 w-5" />
                Watch Preview
              </Button>
            </div>
          </div>
        </div>
      </section>

      {/* Workouts */}
      <section id="workouts" className="py-20">
        <div className="container mx-auto px-4 sm:px-6 lg:px-8">
          <h2 className="mb-6 text-center text-3xl font-bold">Workouts</h2>
          {/* Cards for workouts هنا زي اللي عندك */}
        </div>
      </section>

      {/* Trainers */}
      <section id="trainers" className="bg-muted/30 py-20">
        <div className="container mx-auto px-4 sm:px-6 lg:px-8">
          <h2 className="mb-6 text-center text-3xl font-bold">Our Trainers</h2>
          <div className="grid grid-cols-1 gap-8 md:grid-cols-2 lg:grid-cols-4">
            {trainers.map((t, i) => (
              <Card key={i} className="text-center">
                <CardHeader>
                  <CardTitle>{t.name}</CardTitle>
                  <CardDescription>{t.specialty}</CardDescription>
                </CardHeader>
                <CardContent>
                  <p>{t.experience} Experience</p>
                  <p>{t.clients}+ Clients</p>
                  <p>{t.rating} Rating</p>
                </CardContent>
              </Card>
            ))}
          </div>
        </div>
      </section>

      {/* Pricing */}
      <section id="pricing" className="bg-muted/30 py-20">
        <div className="container mx-auto px-4 sm:px-6 lg:px-8">
          <h2 className="mb-6 text-center text-3xl font-bold">Pricing Plans</h2>
          <div className="mx-auto mb-12 flex max-w-md justify-center space-x-4">
            <Button
              variant={activeTab === "monthly" ? "default" : "outline"}
              onClick={() => setActiveTab("monthly")}
            >
              Monthly
            </Button>
            <Button
              variant={activeTab === "yearly" ? "default" : "outline"}
              onClick={() => setActiveTab("yearly")}
            >
              Yearly (Save 20%)
            </Button>
          </div>

          <div className="mx-auto grid max-w-6xl gap-8 md:grid-cols-3">
            {subscriptionPlans.map((plan, index) => (
              <Card
                key={index}
                className={`flex flex-col justify-between ${
                  plan.popular ? "border-2 border-primary" : ""
                }`}
              >
                <CardHeader>
                  <CardTitle>{plan.name}</CardTitle>
                  <CardDescription>{plan.description}</CardDescription>
                </CardHeader>
                <CardContent>
                  <p className="mb-4 text-4xl font-bold text-primary">
                    {activeTab === "monthly"
                      ? plan.price.monthly
                      : plan.price.yearly}
                  </p>
                  <ul className="space-y-2 text-sm">
                    {plan.features.map((f, i) => (
                      <li key={i} className="flex items-center">
                        <Check className="mr-2 h-4 w-4 text-primary" />
                        {f}
                      </li>
                    ))}
                  </ul>
                </CardContent>
                <CardFooter>
                  <Button className="w-full">Choose {plan.name}</Button>
                </CardFooter>
              </Card>
            ))}
          </div>
        </div>
      </section>
    </main>
  );
} new-1