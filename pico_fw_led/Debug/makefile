################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include src/lib/pico-sdk/src/rp2_common/pico_runtime/subdir.mk
-include src/lib/pico-sdk/src/rp2_common/pico_platform/include/pico/subdir.mk
-include src/lib/pico-sdk/src/rp2_common/pico_platform/subdir.mk
-include src/lib/pico-sdk/src/rp2_common/pico_bootrom/subdir.mk
-include src/lib/pico-sdk/src/rp2_common/hardware_xosc/subdir.mk
-include src/lib/pico-sdk/src/rp2_common/hardware_watchdog/subdir.mk
-include src/lib/pico-sdk/src/rp2_common/hardware_timer/subdir.mk
-include src/lib/pico-sdk/src/rp2_common/hardware_sync/subdir.mk
-include src/lib/pico-sdk/src/rp2_common/hardware_pll/subdir.mk
-include src/lib/pico-sdk/src/rp2_common/hardware_irq/subdir.mk
-include src/lib/pico-sdk/src/rp2_common/hardware_gpio/subdir.mk
-include src/lib/pico-sdk/src/rp2_common/hardware_clocks/subdir.mk
-include src/lib/pico-sdk/src/rp2_common/hardware_claim/subdir.mk
-include src/lib/pico-sdk/src/common/pico_util/subdir.mk
-include src/lib/pico-sdk/src/common/pico_time/subdir.mk
-include src/lib/pico-sdk/src/common/pico_sync/subdir.mk
-include src/hw/driver/subdir.mk
-include src/hw/subdir.mk
-include src/bsp/startup/subdir.mk
-include src/bsp/subdir.mk
-include src/ap/subdir.mk
-include src/subdir.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
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


BUILD_ARTIFACT_NAME := pico_fw_led
BUILD_ARTIFACT_EXTENSION := elf
BUILD_ARTIFACT_PREFIX :=
BUILD_ARTIFACT := $(BUILD_ARTIFACT_PREFIX)$(BUILD_ARTIFACT_NAME)$(if $(BUILD_ARTIFACT_EXTENSION),.$(BUILD_ARTIFACT_EXTENSION),)

# Add inputs and outputs from these tool invocations to the build variables 
SECONDARY_FLASH += \
pico_fw_led.bin \

SECONDARY_SIZE += \
pico_fw_led.siz \


# All Target
all: main-build

# Main-build Target
main-build: pico_fw_led.elf secondary-outputs

# Tool invocations
pico_fw_led.elf: $(OBJS) $(USER_OBJS) makefile objects.mk $(OPTIONAL_TOOL_DEPS)
	@echo 'Building target: $@'
	@echo 'Invoking: GNU Arm Cross C Linker'
	arm-none-eabi-gcc -mcpu=cortex-m0plus -mthumb -O0 -fmessage-length=0 -fsigned-char -ffunction-sections -fdata-sections  -g3 -T "D:\eclipse\eclipse_pico\pico_fw_led\src\bsp\ldscript\pico_flash.ld" -Xlinker --gc-sections -Wl,-Map,"pico_fw_led.map" --specs=nosys.specs -o "pico_fw_led.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '

pico_fw_led.bin: pico_fw_led.elf makefile objects.mk $(OPTIONAL_TOOL_DEPS)
	@echo 'Invoking: GNU Arm Cross Create Flash Image'
	arm-none-eabi-objcopy -O binary "pico_fw_led.elf"  "pico_fw_led.bin"
	@echo 'Finished building: $@'
	@echo ' '

pico_fw_led.siz: pico_fw_led.elf makefile objects.mk $(OPTIONAL_TOOL_DEPS)
	@echo 'Invoking: GNU Arm Cross Print Size'
	arm-none-eabi-size --format=berkeley "pico_fw_led.elf"
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(OBJS)$(SECONDARY_FLASH)$(SECONDARY_SIZE)$(ASM_DEPS)$(S_UPPER_DEPS)$(C_DEPS) pico_fw_led.elf
	-@echo ' '

secondary-outputs: $(SECONDARY_FLASH) $(SECONDARY_SIZE)

.PHONY: all clean dependents main-build

-include ../makefile.targets
