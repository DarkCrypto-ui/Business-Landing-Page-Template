import { Switch, Route } from "wouter";
import { queryClient } from "./lib/queryClient";
import { QueryClientProvider } from "@tanstack/react-query";
import { Toaster } from "@/components/ui/toaster";
import NotFound from "@/pages/not-found";
import Home from "@/pages/Home";
import Resources from "@/pages/Resources";
import Pricing from "@/pages/Pricing";
import Blog from "@/pages/Blog";

function Router() {
  return (
    <Switch>
      <Route path="/" component={Home} />
      <Route path="/resources" component={Resources} />
      <Route path="/pricing" component={Pricing} />
      <Route path="/blog" component={Blog} />
      <Route component={NotFound} />
    </Switch>
  );
}

function App() {
  return (
    <QueryClientProvider client={queryClient}>
      <Router />
      <Toaster />
    </QueryClientProvider>
  );
}

export default App;