<template>
  <DropdownBase
    :location="location"
    :menuButtonIcon="IconMap.CIRCLE_PLUS"
    :menuButtonLabel="$t(`components.dropdown_create.create`)"
    :isMenuButtonUppercase="false"
    menuButtonAriaLabel="components.dropdown_create.create_aria_label"
  >
    <DropdownItemsLayout :location="location" :options="createOptions" />
  </DropdownBase>
</template>

<script setup lang="ts">
import { IconMap } from "~/types/icon-map";
import type { DropdownLocation } from "~/types/location";
import type { MenuSelector } from "~/types/menu/menu-selector";

defineProps<{
  location?: DropdownLocation;
}>();

const createOptions: MenuSelector[] = [
  {
    id: 1,
    label: "_global.new_event",
    routeURL: "/events/create",
    iconURL: `${IconMap.EVENT}`,
    selected: false,
  },
  {
    id: 2,
    label: "components.dropdown_create.new_organization",
    routeURL: "/organizations/create",
    iconURL: "IconOrganization",
    selected: false,
  },
  {
    id: 3,
    label: "_global.new_group",
    routeURL: "/groups/create",
    iconURL: "IconGroup",
    selected: false,
  },
  {
    id: 4,
    label: "_global.new_resource",
    routeURL: "/resources/create",
    iconURL: "IconResource",
    selected: false,
  },
];
</script>
