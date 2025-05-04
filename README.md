import Image from "next/image"
import Link from "next/link"
import { ArrowRight, Menu } from "lucide-react"
import { Button } from "@/components/ui/button"

export default function Home() {
  return (
    <div className="min-h-screen bg-[#111827] text-white">
      {/* Header */}
      <header className="container mx-auto px-4 py-6 flex justify-between items-center">
        <div className="flex items-center gap-2">
          <div className="w-8 h-8 bg-blue-500 rounded-full"></div>
          <span className="text-xl font-bold">Devlink</span>
        </div>

        {/* Mobile menu button */}
        <Button variant="ghost" size="icon" className="md:hidden text-white">
          <Menu className="h-6 w-6" />
        </Button>

        {/* Desktop navigation */}
        <nav className="hidden md:flex items-center gap-8">
          <Link href="#" className="text-gray-300 hover:text-white transition-colors">
            Home
          </Link>
          <Link href="#" className="text-gray-300 hover:text-white transition-colors">
            About
          </Link>
          <Link href="#" className="text-gray-300 hover:text-white transition-colors">
            Services
          </Link>
          <Link href="#" className="text-gray-300 hover:text-white transition-colors">
            Contact
          </Link>
          <Button className="bg-blue-600 hover:bg-blue-700 text-white">Get Started</Button>
        </nav>
      </header>

      {/* Hero Section */}
      <section className="container mx-auto px-4 py-20 flex flex-col md:flex-row items-center gap-12">
        <div className="flex-1 space-y-6">
          <h1 className="text-4xl md:text-6xl font-bold leading-tight">
            Connect with <span className="text-blue-500">developers</span> around the world
          </h1>
          <p className="text-gray-400 text-lg md:text-xl max-w-2xl">
            Join our community of passionate developers to collaborate, learn, and build amazing projects together.
          </p>
          <div className="flex flex-col sm:flex-row gap-4 pt-4">
            <Button className="bg-blue-600 hover:bg-blue-700 text-white px-8 py-6 text-lg">
              Join Now <ArrowRight className="ml-2 h-5 w-5" />
            </Button>
            <Button variant="outline" className="border-gray-600 text-white hover:bg-gray-800 px-8 py-6 text-lg">
              Learn More
            </Button>
          </div>
        </div>
        <div className="flex-1 flex justify-center">
          <div className="relative w-full max-w-md aspect-square">
            <div className="absolute inset-0 bg-blue-500 rounded-full opacity-20 blur-3xl"></div>
            <Image
              src="/placeholder.svg?height=400&width=400"
              alt="Developers connecting"
              width={400}
              height={400}
              className="relative z-10"
            />
          </div>
        </div>
      </section>

      {/* Features Section */}
      <section className="container mx-auto px-4 py-20">
        <div className="text-center mb-16">
          <h2 className="text-3xl md:text-4xl font-bold mb-4">Why Choose Devlink?</h2>
          <p className="text-gray-400 max-w-2xl mx-auto">
            We provide the tools and community you need to grow as a developer
          </p>
        </div>

        <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
          {[
            {
              title: "Global Community",
              description: "Connect with developers from around the world and expand your network.",
            },
            {
              title: "Collaborative Projects",
              description: "Find teammates and work on exciting projects to build your portfolio.",
            },
            {
              title: "Learning Resources",
              description: "Access tutorials, workshops, and mentorship to improve your skills.",
            },
          ].map((feature, index) => (
            <div key={index} className="bg-gray-800 rounded-xl p-8 transition-transform hover:scale-105">
              <div className="w-12 h-12 bg-blue-600 rounded-lg mb-6 flex items-center justify-center">
                <span className="text-2xl font-bold">{index + 1}</span>
              </div>
              <h3 className="text-xl font-bold mb-3">{feature.title}</h3>
              <p className="text-gray-400">{feature.description}</p>
            </div>
          ))}
        </div>
      </section>

      {/* CTA Section */}
      <section className="container mx-auto px-4 py-20">
        <div className="bg-gradient-to-r from-blue-600 to-blue-800 rounded-2xl p-12 text-center">
          <h2 className="text-3xl md:text-4xl font-bold mb-4">Ready to join our community?</h2>
          <p className="text-blue-100 max-w-2xl mx-auto mb-8">
            Start your journey today and connect with thousands of developers worldwide.
          </p>
          <Button className="bg-white text-blue-700 hover:bg-gray-100 px-8 py-6 text-lg">
            Sign Up Now <ArrowRight className="ml-2 h-5 w-5" />
          </Button>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-gray-900 py-12">
        <div className="container mx-auto px-4">
          <div className="flex flex-col md:flex-row justify-between items-center">
            <div className="flex items-center gap-2 mb-6 md:mb-0">
              <div className="w-8 h-8 bg-blue-500 rounded-full"></div>
              <span className="text-xl font-bold">Devlink</span>
            </div>
            <div className="flex gap-6">
              <Link href="#" className="text-gray-400 hover:text-white transition-colors">
                Terms
              </Link>
              <Link href="#" className="text-gray-400 hover:text-white transition-colors">
                Privacy
              </Link>
              <Link href="#" className="text-gray-400 hover:text-white transition-colors">
                Cookies
              </Link>
            </div>
          </div>
          <div className="border-t border-gray-800 mt-8 pt-8 text-center md:text-left text-gray-500">
            © 2023 Devlink. All rights reserved.
          </div>
        </div>
      </footer>
    </div>
  )
}
