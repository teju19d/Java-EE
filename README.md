# Java-EE
package mypack;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.ModelAttribute;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.servlet.ModelAndView;

@Controller
public class PersonController {
	@GetMapping("person")
	public ModelAndView before()
	{
 		Person defaultPerson=new Person();
	
		return new ModelAndView("Person","persons",defaultPerson);
	}
	
	@PostMapping("person")
	public String afterSubmit(
		@ModelAttribute("pr") Person person) 
	{
		//return form success view
		System.out.println("inside afterSubmit\t"+person);
		return "View";
	}
}

