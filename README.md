# VulkanTutorial

`pAllocator` is always `nullptr` in this tutorial



# Validation layers

```c++
std::vector<const char*> getRequiredExtensions()
{
    uint32_t     glfwExtensionCount = 0;
    const char** glfwExtensions;
    glfwExtensions = glfwGetRequiredInstanceExtensions(&glfwExtensionCount);
	
    // what the heck is this?
    std::vector<const char*> extensions(glfwExtensions, glfwExtensions + glfwExtensionCount);

    if (enableValidationLayers)
    {
        extensions.push_back(VK_EXT_DEBUG_UTILS_EXTENSION_NAME);
    }

    return extensions;
}
```

https://stackoverflow.com/questions/56430948/which-stdvector-constructor-is-used-here

![image-20220630225107684](images/image-20220630225107684.png)

---

By saying:

> Add a new static member function called `debugCallback` **with the `PFN_vkDebugUtilsMessengerCallbackEXT` prototype**,

they mean our function:

![image-20220630230155122](images/image-20220630230155122.png)

 has the following signature (defined in `vulkan_core.h`): 

![image-20220630230122560](images/image-20220630230122560.png)

---

