# Strategy
```cs
interface IStrategy { void Execute(); }

class StrategyA : IStrategy { public void Execute()=>Console.WriteLine("A"); }
class StrategyB : IStrategy { public void Execute()=>Console.WriteLine("B"); }

class Context {
    private IStrategy s;
    public Context(IStrategy s){this.s=s;}
    public void Run()=>s.Execute();
}

class Program { static void Main()=>new Context(new StrategyB()).Run(); }
