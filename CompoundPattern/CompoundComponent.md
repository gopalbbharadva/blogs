<!-- # Patterns in react : Compound component -->
# React design pattern : Compound component

- Introduction
- What is compound pattern?
- What problem it's solving?
- Solution of compound pattern.
  - Make accordion component
  - Styling accordion component
- Pros & Cons
- Conclusion


## Introduction

Hey readers, in this blog we will see about one of the best react pattern which is compound pattern. patterns are like th
```
type AccordionPropsType = {
  children: React.ReactNode;
  title: string;
  toggleAccordion: () => void;
  isAccordionExpanded: boolean;
};

export const Accordion = ({
  children,
  isAccordionExpanded,
  title,
  toggleAccordion,
}: AccordionPropsType) => {
  return (
    <div className="">
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