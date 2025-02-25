import { motion } from "framer-motion";
import { Card } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { FileText, Video, BookOpen } from "lucide-react";
import GridPattern from "@/components/ui/patterns/GridPattern";
import Header from "@/components/layout/Header";

const resources = [
  {
    icon: FileText,
    title: "Documentation",
    description: "Comprehensive guides and API references",
    link: "#"
  },
  {
    icon: Video,
    title: "Video Tutorials",
    description: "Step-by-step learning resources",
    link: "#"
  },
  {
    icon: BookOpen,
    title: "Case Studies",
    description: "Real-world implementation stories",
    link: "#"
  }
];

export default function Resources() {
  return (
    <div className="bg-black min-h-screen">
      <Header />
      <div className="relative pt-20">
        <GridPattern />
        
        <div className="container mx-auto px-6 py-24">
          <motion.div
            initial={{ opacity: 0, y: 20 }}
            animate={{ opacity: 1, y: 0 }}
            transition={{ duration: 0.8 }}
            className="max-w-3xl mx-auto text-center mb-16"
          >
            <h1 className="text-4xl font-bold text-white mb-6">Resources</h1>
            <p className="text-gray-400 text-lg">
              Everything you need to get the most out of our platform
            </p>
          </motion.div>

          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mt-12">
            {resources.map((resource, index) => (
              <motion.div
                key={index}
                initial={{ opacity: 0, y: 20 }}
                animate={{ opacity: 1, y: 0 }}
                transition={{ duration: 0.5, delay: index * 0.1 }}
              >
                <Card className="p-6 bg-gray-900/50 backdrop-blur-lg border-gray-800 hover:bg-gray-900/70 transition-all duration-300">
                  <resource.icon className="w-12 h-12 text-white mb-4" />
                  <h3 className="text-xl font-semibold text-white mb-2">
                    {resource.title}
                  </h3>
                  <p className="text-gray-400 mb-4">
                    {resource.description}
                  </p>
                  <Button variant="secondary" className="w-full">
                    Learn More
                  </Button>
                </Card>
              </motion.div>
            ))}
          </div>
        </div>
      </div>
    </div>
  );
}
