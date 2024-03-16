<!-- type AccordionPropsType = {
  children: React.ReactNode;
  title: string;
  toggleAccordion: () => void;
  isAccordionExpanded: boolean;
}; -->

<!-- # Patterns in react : Compound component -->
# React design pattern : Compound component

- Introduction
  - What is design pattern?
- What is compound pattern in react?
- What problem it's solving?
  - Problem with accordion component
- Solution of compound pattern.
  - Make accordion component
  - Styling accordion component
- Pros & Cons
- Conclusion


## Introduction

Hey readers, in this blog we will see about one of the best 
react pattern which is **compound pattern** .

### What is design pattern?
In software engineering, design patterns are solutions for commonly reoccurring problems. it
provides flexibility, modularity and scalability to a developer's code.

Let's take basic example to understand. let's say you are fetching user details on the home page. you wrote a code to handle loading,data and error state in the home page file before JSX. so here
what you can do is you can move that data fetching part in one custom hook and get the required
states from custom hook. so now you can use that hook wherever in your project to fetch the user 
details.

<!-- Quote -->
So in above example we have used one of the react design pattern which is **hooks**. here 
to use users details in other places is the commonly occurring problem. we used **hooks** design 
pattern to solve that problem.

## What is compound pattern react?
- Compound pattern is a pattern in react where groups of components make one single 
  component by sharing the state implicitly.

- It's like dropdown component where **select** and **option** component build 
  **dropdown** component by sharing the state internally.

## What problem it's solving?
- Usually i used to create a accordion component like this. 
<!-- - Below is the example of basic **accordion** component. -->

```
export const Accordion = ({
  children,
  isAccordionExpanded,
  title,
  toggleAccordion,
}: AccordionPropsType) => {
  return (
    <div>
      <div onClick={toggleAccordion}>
        {title}
        <button>
          <button>{isAccordionExpanded ? "+" : "-"}</button>
        </button>
      </div>
      {isAccordionExpanded && <div>{children}</div>}
    </div>
  );
};
```

```
<Accordion
  title="Closed Tickets"
  toggleAccordion={toggleCloseTicketsAccordion}
  isAccordionExpanded={isExpandCloseTicketsAccordion}
> 
  <p>
    What is Devin AI software? Devin is a smart tool that helps with coding by itself. It can
    understand what you want to make, write the code, find and fix errors, and get better over
    time by learning.
  </p>
 </Accordion>
```

> Can you find the problems in above example?
- **First problem**: According to how it's rendered if we want to render 10 accordions we need
  to create 10 different states for each of them as we are passing state and it's handler
  separately.So it's not **scalable**

- **Second problem**: if we want to change the icon for close and open state of accordion then
  we can't modify it so first problem is it's not **flexible to change**.

- **Third problem**: if we have some icon or bold text that we want to render it as title then 
  we can't as we are expecting string. so it's **not scalable and not adaptive for new change**.


  