# Code generation


What do we want the model to generate?

Ideally, it should be usecases based on the specification mentioned earlier.

How are we going to evaluate the result of the generated code?


1. constraint. We can set stricter prompts, aka generating specific code such as protobuf or json schema that could also further generate code and language agnostic client/server code. Also, anything with schemas could be easily validates using linters without needing to actually execute the code.
2. executing code. We need to prepare sandboxed environment that could execute code safely, such as docker etc. If thr code executes, it is successful.
3. linters and fixers. Another metric is to evaluate the linter errors generated, or the number of fixes. The code can be send to the prompt for multiple times until the code is fixed or has minimal warnings etc
4. test cases. The more useful test cases that the code covers, the better. Test cases can be designed by both humans and AI. It is preferable to have humans provide more examples, even if the AI could do that.
5. coverage. A higher code coverage indicates a better output.
6. Line of code. Although we can focus on less line of code, we want to avoid scenarios where the code generated is unreadable.
7. documented. Generated documentation and examples means higher quality code
8. comments. Comments is a must
9. code review. Use another AI to do code review and suggest improvements. The number of improvements suggested could be a metric.

Instead of just depending on one single model to generate, we can send the prompts to multiple models in parallel and return the best result based on our evaluation metrics.

Also, instead of just going through a single round of generation, we can take inspiration from adversarial network and also have an AI that does code review. So the code wull be feed through the model multiple times and possibly going through multiple iterations before producing the final output.




