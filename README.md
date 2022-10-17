
# infinity-scroll-vue3

Hi, my name is Eray. I produced this component for my own needs and decided to publish it for others who might need it.

You have to install vue3 and vue-toastification to use it.

After installing Vue-Toastification, you can start using it.

What does this component do? It runs the function you want when the scroll end is reached in the class whose selector you define.

You have to provide 3 things that the component requests.

1 - scrollClass: The class you want to listen the scroll event(example: ".data-table")

2 - handleScroll: This should be the function you want to run when the scroll comes to the end.

3 - listEnd: This state should be a boolean to keep you at the end of the list. According to the length of the array coming from the service, you should understand that it comes to the end of the list and you should declare this variable to this component.

I wish you good work :)
