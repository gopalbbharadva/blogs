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
- Below is the example of basic **accordion** component.

```
export const Accordion = ({
  children,
  isAccordionExpanded,
  title,
  toggleAccordion,
}: AccordionPropsType) => {
  return (
    <div>
      <div onClick={toggleAccordion} className="">
        {title}
        <button>
          <button>{isAccordionExpanded ? "+" : "-"}</button>
        </button>
      </div>
      {isAccordionExpanded && <div className="">{children}</div>}
    </div>
  );
};
```