import { motion } from "framer-motion";

export default function WavePattern() {
  return (
    <svg
      className="absolute inset-0 -z-10"
      width="100%"
      height="100%"
      xmlns="http://www.w3.org/2000/svg"
    >
      <defs>
        <linearGradient id="wave-gradient" x1="0%" y1="0%" x2="100%" y2="0%">
          <stop offset="0%" stopColor="rgba(99,102,241,0.1)" />
          <stop offset="50%" stopColor="rgba(168,85,247,0.1)" />
          <stop offset="100%" stopColor="rgba(236,72,153,0.1)" />
        </linearGradient>
      </defs>
      <motion.path
        initial={{ pathLength: 0, opacity: 0 }}
        animate={{ pathLength: 1, opacity: 1 }}
        transition={{ duration: 2, ease: "easeInOut" }}
        d="M0 50 Q 250 0, 500 50 T 1000 50"
        stroke="url(#wave-gradient)"
        strokeWidth="2"
        fill="none"
      />
    </svg>
  );
}
