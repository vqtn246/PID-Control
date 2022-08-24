################################################################################
# Automatically-generated file. Do not edit!
# Toolchain: GNU Tools for STM32 (9-2020-q2-update)
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include Drivers/STM32F1xx_HAL_Driver/Src/subdir.mk
-include Core/Startup/subdir.mk
-include Core/Src/subdir.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

OPTIONAL_TOOL_DEPS := \
$(wildcard ../makefile.defs) \
$(wildcard ../makefile.init) \
$(wildcard ../makefile.targets) \


BUILD_ARTIFACT_NAME := Motor_control_final
BUILD_ARTIFACT_EXTENSION := elf
BUILD_ARTIFACT_PREFIX :=
BUILD_ARTIFACT := $(BUILD_ARTIFACT_PREFIX)$(BUILD_ARTIFACT_NAME)$(if $(BUILD_ARTIFACT_EXTENSION),.$(BUILD_ARTIFACT_EXTENSION),)

# Add inputs and outputs from these tool invocations to the build variables 
EXECUTABLES += \
Motor_control_final.elf \

SIZE_OUTPUT += \
default.size.stdout \

OBJDUMP_LIST += \
Motor_control_final.list \

OBJCOPY_HEX += \
Motor_control_final.hex \

OBJCOPY_BIN += \
Motor_control_final.bin \


# All Target
all: main-build

# Main-build Target
main-build: Motor_control_final.elf secondary-outputs

# Tool invocations
Motor_control_final.elf: $(OBJS) $(USER_OBJS) C:\Users\ACER\STM32CubeIDE\Motor_control_final\STM32F103C8TX_FLASH.ld makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-gcc -o "Motor_control_final.elf" @"objects.list" $(USER_OBJS) $(LIBS) -mcpu=cortex-m3 -T"C:\Users\ACER\STM32CubeIDE\Motor_control_final\STM32F103C8TX_FLASH.ld" --specs=nosys.specs -Wl,-Map="Motor_control_final.map" -Wl,--gc-sections -static --specs=nano.specs -mfloat-abi=soft -mthumb -u _printf_float -u _scanf_float -Wl,--start-group -lc -lm -Wl,--end-group
	@echo 'Finished building target: $@'
	@echo ' '

default.size.stdout: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-size  $(EXECUTABLES)
	@echo 'Finished building: $@'
	@echo ' '

Motor_control_final.list: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-objdump -h -S $(EXECUTABLES) > "Motor_control_final.list"
	@echo 'Finished building: $@'
	@echo ' '

Motor_control_final.hex: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-objcopy  -O ihex $(EXECUTABLES) "Motor_control_final.hex"
	@echo 'Finished building: $@'
	@echo ' '

Motor_control_final.bin: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-objcopy  -O binary $(EXECUTABLES) "Motor_control_final.bin"
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(OBJCOPY_HEX)$(SIZE_OUTPUT)$(OBJDUMP_LIST)$(EXECUTABLES)$(OBJS)$(S_DEPS)$(S_UPPER_DEPS)$(C_DEPS)$(OBJCOPY_BIN) Motor_control_final.elf
	-@echo ' '

secondary-outputs: $(SIZE_OUTPUT) $(OBJDUMP_LIST) $(OBJCOPY_HEX) $(OBJCOPY_BIN)

fail-specified-linker-script-missing:
	@echo 'Error: Cannot find the specified linker script. Check the linker settings in the build configuration.'
	@exit 2

warn-no-linker-script-specified:
	@echo 'Warning: No linker script specified. Check the linker settings in the build configuration.'

.PHONY: all clean dependents fail-specified-linker-script-missing warn-no-linker-script-specified

-include ../makefile.targets
