<script setup lang="ts">
import { Button } from '@/components/ui/button'
import { Switch } from '@/components/ui/switch'
import { Label } from '@/components/ui/label'
import { Avatar, AvatarFallback, AvatarImage } from '@/components/ui/avatar'
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuLabel,
  DropdownMenuSeparator,
  DropdownMenuTrigger,
} from '@/components/ui/dropdown-menu'
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from '@/components/ui/card'
import {
  Dialog,
  DialogContent,
  DialogDescription,
  DialogFooter,
  DialogHeader,
  DialogTitle,
  DialogTrigger,
} from '@/components/ui/dialog'
import {
  Sheet,
  SheetContent,
  SheetDescription,
  SheetHeader,
  SheetTitle,
  SheetTrigger,
} from '@/components/ui/sheet'
import { ref, watch } from 'vue'
import {
  Collapsible,
  CollapsibleContent,
  CollapsibleTrigger,
} from '@/components/ui/collapsible'
import { Badge } from '@/components/ui/badge'
// import { Accordion, AccordionContent, AccordionItem, AccordionTrigger } from '@/components/ui/accordion'

// const defaultValue = ['item-3', 'item-4']

// const accordionItems = [
//   { value: 'item-1', title: 'Is it accessible?', content: 'Yes. It adheres to the WAI-ARIA design pattern.' },
//   { value: 'item-2', title: 'Is it unstyled?', content: 'Yes. It\'s unstyled by default, giving you freedom over the look and feel.' },
//   { value: 'item-3', title: 'Can it be animated?', content: 'Yes! You can use the transition prop to configure the animation.' },
// ]
const isOpen = ref(false)

const mode = ref('light')
const toggleMode = () => {
  mode.value = mode.value === 'light' ? 'dark' : 'light'
}
</script>

<template>
  <div class="layout-container bg-background p-2" :class="mode">
    <div class="flex flex-1 items-center justify-end px-2">
      <div class="mr-3">
        <Sheet>
          <SheetTrigger>
            <svg class="text-primary" width="24" height="24" viewBox="0 0 15 15" fill="none"
              xmlns="http://www.w3.org/2000/svg">
              <path
                d="M4.5 1C4.77614 1 5 1.22386 5 1.5V2H10V1.5C10 1.22386 10.2239 1 10.5 1C10.7761 1 11 1.22386 11 1.5V2H12.5C13.3284 2 14 2.67157 14 3.5V12.5C14 13.3284 13.3284 14 12.5 14H2.5C1.67157 14 1 13.3284 1 12.5V3.5C1 2.67157 1.67157 2 2.5 2H4V1.5C4 1.22386 4.22386 1 4.5 1ZM10 3V3.5C10 3.77614 10.2239 4 10.5 4C10.7761 4 11 3.77614 11 3.5V3H12.5C12.7761 3 13 3.22386 13 3.5V5H2V3.5C2 3.22386 2.22386 3 2.5 3H4V3.5C4 3.77614 4.22386 4 4.5 4C4.77614 4 5 3.77614 5 3.5V3H10ZM2 6V12.5C2 12.7761 2.22386 13 2.5 13H12.5C12.7761 13 13 12.7761 13 12.5V6H2ZM7 7.5C7 7.22386 7.22386 7 7.5 7C7.77614 7 8 7.22386 8 7.5C8 7.77614 7.77614 8 7.5 8C7.22386 8 7 7.77614 7 7.5ZM9.5 7C9.22386 7 9 7.22386 9 7.5C9 7.77614 9.22386 8 9.5 8C9.77614 8 10 7.77614 10 7.5C10 7.22386 9.77614 7 9.5 7ZM11 7.5C11 7.22386 11.2239 7 11.5 7C11.7761 7 12 7.22386 12 7.5C12 7.77614 11.7761 8 11.5 8C11.2239 8 11 7.77614 11 7.5ZM11.5 9C11.2239 9 11 9.22386 11 9.5C11 9.77614 11.2239 10 11.5 10C11.7761 10 12 9.77614 12 9.5C12 9.22386 11.7761 9 11.5 9ZM9 9.5C9 9.22386 9.22386 9 9.5 9C9.77614 9 10 9.22386 10 9.5C10 9.77614 9.77614 10 9.5 10C9.22386 10 9 9.77614 9 9.5ZM7.5 9C7.22386 9 7 9.22386 7 9.5C7 9.77614 7.22386 10 7.5 10C7.77614 10 8 9.77614 8 9.5C8 9.22386 7.77614 9 7.5 9ZM5 9.5C5 9.22386 5.22386 9 5.5 9C5.77614 9 6 9.22386 6 9.5C6 9.77614 5.77614 10 5.5 10C5.22386 10 5 9.77614 5 9.5ZM3.5 9C3.22386 9 3 9.22386 3 9.5C3 9.77614 3.22386 10 3.5 10C3.77614 10 4 9.77614 4 9.5C4 9.22386 3.77614 9 3.5 9ZM3 11.5C3 11.2239 3.22386 11 3.5 11C3.77614 11 4 11.2239 4 11.5C4 11.7761 3.77614 12 3.5 12C3.22386 12 3 11.7761 3 11.5ZM5.5 11C5.22386 11 5 11.2239 5 11.5C5 11.7761 5.22386 12 5.5 12C5.77614 12 6 11.7761 6 11.5C6 11.2239 5.77614 11 5.5 11ZM7 11.5C7 11.2239 7.22386 11 7.5 11C7.77614 11 8 11.2239 8 11.5C8 11.7761 7.77614 12 7.5 12C7.22386 12 7 11.7761 7 11.5ZM9.5 11C9.22386 11 9 11.2239 9 11.5C9 11.7761 9.22386 12 9.5 12C9.77614 12 10 11.7761 10 11.5C10 11.2239 9.77614 11 9.5 11Z"
                fill="currentColor" fill-rule="evenodd" clip-rule="evenodd"></path>
            </svg>
            <!-- Calendar -->
          </SheetTrigger>
          <SheetContent>
            <SheetHeader>
              <SheetTitle>行事曆 / 日程表</SheetTitle>
              <!-- <SheetDescription>
                This action cannot be undone. This will permanently delete your account
                and remove your data from our servers.
              </SheetDescription> -->
            </SheetHeader>
          </SheetContent>
        </Sheet>
      </div>
      <div class="mr-3">
        <button>
          <svg class="dark:text-white" width="24" height="24" viewBox="0 0 15 15" fill="none"
            xmlns="http://www.w3.org/2000/svg">
            <path
              d="M8.60124 1.25086C8.60124 1.75459 8.26278 2.17927 7.80087 2.30989C10.1459 2.4647 12 4.41582 12 6.79999V10.25C12 11.0563 12.0329 11.7074 12.7236 12.0528C12.931 12.1565 13.0399 12.3892 12.9866 12.6149C12.9333 12.8406 12.7319 13 12.5 13H8.16144C8.36904 13.1832 8.49997 13.4513 8.49997 13.75C8.49997 14.3023 8.05226 14.75 7.49997 14.75C6.94769 14.75 6.49997 14.3023 6.49997 13.75C6.49997 13.4513 6.63091 13.1832 6.83851 13H2.49999C2.2681 13 2.06664 12.8406 2.01336 12.6149C1.96009 12.3892 2.06897 12.1565 2.27638 12.0528C2.96708 11.7074 2.99999 11.0563 2.99999 10.25V6.79999C2.99999 4.41537 4.85481 2.46396 7.20042 2.3098C6.73867 2.17908 6.40036 1.75448 6.40036 1.25086C6.40036 0.643104 6.89304 0.150421 7.5008 0.150421C8.10855 0.150421 8.60124 0.643104 8.60124 1.25086ZM7.49999 3.29999C5.56699 3.29999 3.99999 4.86699 3.99999 6.79999V10.25L4.00002 10.3009C4.0005 10.7463 4.00121 11.4084 3.69929 12H11.3007C10.9988 11.4084 10.9995 10.7463 11 10.3009L11 10.25V6.79999C11 4.86699 9.43299 3.29999 7.49999 3.29999Z"
              fill="currentColor" fill-rule="evenodd" clip-rule="evenodd"></path>
          </svg>
        </button>
      </div>
      <div class="mr-3">
        <div class="flex items-center space-x-2">
          <Label for="airplane-mode" @click="toggleMode">
            <svg v-if="mode === 'light'" width="24" height="24" viewBox="0 0 15 15" fill="none"
              xmlns="http://www.w3.org/2000/svg">
              <path
                d="M7.5 0C7.77614 0 8 0.223858 8 0.5V2.5C8 2.77614 7.77614 3 7.5 3C7.22386 3 7 2.77614 7 2.5V0.5C7 0.223858 7.22386 0 7.5 0ZM2.1967 2.1967C2.39196 2.00144 2.70854 2.00144 2.90381 2.1967L4.31802 3.61091C4.51328 3.80617 4.51328 4.12276 4.31802 4.31802C4.12276 4.51328 3.80617 4.51328 3.61091 4.31802L2.1967 2.90381C2.00144 2.70854 2.00144 2.39196 2.1967 2.1967ZM0.5 7C0.223858 7 0 7.22386 0 7.5C0 7.77614 0.223858 8 0.5 8H2.5C2.77614 8 3 7.77614 3 7.5C3 7.22386 2.77614 7 2.5 7H0.5ZM2.1967 12.8033C2.00144 12.608 2.00144 12.2915 2.1967 12.0962L3.61091 10.682C3.80617 10.4867 4.12276 10.4867 4.31802 10.682C4.51328 10.8772 4.51328 11.1938 4.31802 11.3891L2.90381 12.8033C2.70854 12.9986 2.39196 12.9986 2.1967 12.8033ZM12.5 7C12.2239 7 12 7.22386 12 7.5C12 7.77614 12.2239 8 12.5 8H14.5C14.7761 8 15 7.77614 15 7.5C15 7.22386 14.7761 7 14.5 7H12.5ZM10.682 4.31802C10.4867 4.12276 10.4867 3.80617 10.682 3.61091L12.0962 2.1967C12.2915 2.00144 12.608 2.00144 12.8033 2.1967C12.9986 2.39196 12.9986 2.70854 12.8033 2.90381L11.3891 4.31802C11.1938 4.51328 10.8772 4.51328 10.682 4.31802ZM8 12.5C8 12.2239 7.77614 12 7.5 12C7.22386 12 7 12.2239 7 12.5V14.5C7 14.7761 7.22386 15 7.5 15C7.77614 15 8 14.7761 8 14.5V12.5ZM10.682 10.682C10.8772 10.4867 11.1938 10.4867 11.3891 10.682L12.8033 12.0962C12.9986 12.2915 12.9986 12.608 12.8033 12.8033C12.608 12.9986 12.2915 12.9986 12.0962 12.8033L10.682 11.3891C10.4867 11.1938 10.4867 10.8772 10.682 10.682ZM5.5 7.5C5.5 6.39543 6.39543 5.5 7.5 5.5C8.60457 5.5 9.5 6.39543 9.5 7.5C9.5 8.60457 8.60457 9.5 7.5 9.5C6.39543 9.5 5.5 8.60457 5.5 7.5ZM7.5 4.5C5.84315 4.5 4.5 5.84315 4.5 7.5C4.5 9.15685 5.84315 10.5 7.5 10.5C9.15685 10.5 10.5 9.15685 10.5 7.5C10.5 5.84315 9.15685 4.5 7.5 4.5Z"
                fill="currentColor" fill-rule="evenodd" clip-rule="evenodd"></path>
            </svg>
            <svg v-else width="24" height="24" viewBox="0 0 15 15" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path
                d="M2.89998 0.499976C2.89998 0.279062 2.72089 0.0999756 2.49998 0.0999756C2.27906 0.0999756 2.09998 0.279062 2.09998 0.499976V1.09998H1.49998C1.27906 1.09998 1.09998 1.27906 1.09998 1.49998C1.09998 1.72089 1.27906 1.89998 1.49998 1.89998H2.09998V2.49998C2.09998 2.72089 2.27906 2.89998 2.49998 2.89998C2.72089 2.89998 2.89998 2.72089 2.89998 2.49998V1.89998H3.49998C3.72089 1.89998 3.89998 1.72089 3.89998 1.49998C3.89998 1.27906 3.72089 1.09998 3.49998 1.09998H2.89998V0.499976ZM5.89998 3.49998C5.89998 3.27906 5.72089 3.09998 5.49998 3.09998C5.27906 3.09998 5.09998 3.27906 5.09998 3.49998V4.09998H4.49998C4.27906 4.09998 4.09998 4.27906 4.09998 4.49998C4.09998 4.72089 4.27906 4.89998 4.49998 4.89998H5.09998V5.49998C5.09998 5.72089 5.27906 5.89998 5.49998 5.89998C5.72089 5.89998 5.89998 5.72089 5.89998 5.49998V4.89998H6.49998C6.72089 4.89998 6.89998 4.72089 6.89998 4.49998C6.89998 4.27906 6.72089 4.09998 6.49998 4.09998H5.89998V3.49998ZM1.89998 6.49998C1.89998 6.27906 1.72089 6.09998 1.49998 6.09998C1.27906 6.09998 1.09998 6.27906 1.09998 6.49998V7.09998H0.499976C0.279062 7.09998 0.0999756 7.27906 0.0999756 7.49998C0.0999756 7.72089 0.279062 7.89998 0.499976 7.89998H1.09998V8.49998C1.09998 8.72089 1.27906 8.89997 1.49998 8.89997C1.72089 8.89997 1.89998 8.72089 1.89998 8.49998V7.89998H2.49998C2.72089 7.89998 2.89998 7.72089 2.89998 7.49998C2.89998 7.27906 2.72089 7.09998 2.49998 7.09998H1.89998V6.49998ZM8.54406 0.98184L8.24618 0.941586C8.03275 0.917676 7.90692 1.1655 8.02936 1.34194C8.17013 1.54479 8.29981 1.75592 8.41754 1.97445C8.91878 2.90485 9.20322 3.96932 9.20322 5.10022C9.20322 8.37201 6.82247 11.0878 3.69887 11.6097C3.45736 11.65 3.20988 11.6772 2.96008 11.6906C2.74563 11.702 2.62729 11.9535 2.77721 12.1072C2.84551 12.1773 2.91535 12.2458 2.98667 12.3128L3.05883 12.3795L3.31883 12.6045L3.50684 12.7532L3.62796 12.8433L3.81491 12.9742L3.99079 13.089C4.11175 13.1651 4.23536 13.2375 4.36157 13.3059L4.62496 13.4412L4.88553 13.5607L5.18837 13.6828L5.43169 13.7686C5.56564 13.8128 5.70149 13.8529 5.83857 13.8885C5.94262 13.9155 6.04767 13.9401 6.15405 13.9622C6.27993 13.9883 6.40713 14.0109 6.53544 14.0298L6.85241 14.0685L7.11934 14.0892C7.24637 14.0965 7.37436 14.1002 7.50322 14.1002C11.1483 14.1002 14.1032 11.1453 14.1032 7.50023C14.1032 7.25044 14.0893 7.00389 14.0623 6.76131L14.0255 6.48407C13.991 6.26083 13.9453 6.04129 13.8891 5.82642C13.8213 5.56709 13.7382 5.31398 13.6409 5.06881L13.5279 4.80132L13.4507 4.63542L13.3766 4.48666C13.2178 4.17773 13.0353 3.88295 12.8312 3.60423L12.6782 3.40352L12.4793 3.16432L12.3157 2.98361L12.1961 2.85951L12.0355 2.70246L11.8134 2.50184L11.4925 2.24191L11.2483 2.06498L10.9562 1.87446L10.6346 1.68894L10.3073 1.52378L10.1938 1.47176L9.95488 1.3706L9.67791 1.2669L9.42566 1.1846L9.10075 1.09489L8.83599 1.03486L8.54406 0.98184ZM10.4032 5.30023C10.4032 4.27588 10.2002 3.29829 9.83244 2.40604C11.7623 3.28995 13.1032 5.23862 13.1032 7.50023C13.1032 10.593 10.596 13.1002 7.50322 13.1002C6.63646 13.1002 5.81597 12.9036 5.08355 12.5522C6.5419 12.0941 7.81081 11.2082 8.74322 10.0416C8.87963 10.2284 9.10028 10.3497 9.34928 10.3497C9.76349 10.3497 10.0993 10.0139 10.0993 9.59971C10.0993 9.24256 9.84965 8.94373 9.51535 8.86816C9.57741 8.75165 9.63653 8.63334 9.6926 8.51332C9.88358 8.63163 10.1088 8.69993 10.35 8.69993C11.0403 8.69993 11.6 8.14028 11.6 7.44993C11.6 6.75976 11.0406 6.20024 10.3505 6.19993C10.3853 5.90487 10.4032 5.60464 10.4032 5.30023Z"
                fill="currentColor" fill-rule="evenodd" clip-rule="evenodd"></path>
            </svg>
          </Label>
          <!-- <Switch id="airplane-mode" @update:checked="toggleMode" /> -->
        </div>
      </div>
      <div class="">
        <DropdownMenu>
          <DropdownMenuTrigger>
            <Avatar>
              <AvatarImage src="https://ui.shadcn.com/avatars/02.png" alt="@radix-vue" />
              <AvatarFallback>B</AvatarFallback>
            </Avatar>
          </DropdownMenuTrigger>
          <DropdownMenuContent>
            <DropdownMenuLabel>我的帳號</DropdownMenuLabel>
            <DropdownMenuSeparator />
            <DropdownMenuItem>帳號資訊</DropdownMenuItem>
            <DropdownMenuItem>密碼修改</DropdownMenuItem>
          </DropdownMenuContent>
        </DropdownMenu>
      </div>
    </div>
    <div class="grid lg:grid-cols-5 mt-[40px]">
      <div class="pb-12 hidden lg:block">
        <div class="space-y-4 py-4">
          <div class="flex flex-col px-3">
            <Dialog>
              <DialogTrigger>
                <div class="flex items-center justify-center mx-auto bg-secondary rounded-md h-[36px]">
                  <div class="icon mr-3">
                    <svg class="text-primary" width="24" height="24" viewBox="0 0 15 15" fill="none"
                      xmlns="http://www.w3.org/2000/svg">
                      <path
                        d="M4.5 1C4.22386 1 4 1.22386 4 1.5C4 1.77614 4.22386 2 4.5 2H12V13H4.5C4.22386 13 4 13.2239 4 13.5C4 13.7761 4.22386 14 4.5 14H12C12.5523 14 13 13.5523 13 13V2C13 1.44772 12.5523 1 12 1H4.5ZM6.60355 4.89645C6.40829 4.70118 6.09171 4.70118 5.89645 4.89645C5.70118 5.09171 5.70118 5.40829 5.89645 5.60355L7.29289 7H0.5C0.223858 7 0 7.22386 0 7.5C0 7.77614 0.223858 8 0.5 8H7.29289L5.89645 9.39645C5.70118 9.59171 5.70118 9.90829 5.89645 10.1036C6.09171 10.2988 6.40829 10.2988 6.60355 10.1036L8.85355 7.85355C9.04882 7.65829 9.04882 7.34171 8.85355 7.14645L6.60355 4.89645Z"
                        fill="currentColor" fill-rule="evenodd" clip-rule="evenodd"></path>
                    </svg>
                  </div>
                  <p class="text-primary text-[16px]">
                    打卡
                  </p>
                </div>
              </DialogTrigger>
              <DialogContent>
                <DialogHeader>
                  <DialogTitle>
                    <div class="flex justify-center">
                      <p>2023 / 09 / 22</p>
                    </div>
                  </DialogTitle>
                  <DialogDescription>
                    <div class="flex flex-col items-center justify-center">
                      <p>08:59</p>
                      <p>UTC+8</p>
                    </div>
                  </DialogDescription>
                </DialogHeader>
                <DialogFooter class="text-center mx-auto">
                  <Button class="mr-2">上班</Button>
                  <Button variant="outline">下班</Button>
                </DialogFooter>
              </DialogContent>
            </Dialog>
          </div>
          <div class="px-3 py-2">
            <div class="space-y-1">
              <a
                class="inline-flex items-center rounded-md text-sm font-medium transition-colors focus-visible:outline-none focus-visible:ring-1 focus-visible:ring-ring disabled:pointer-events-none disabled:opacity-50 text-primary hover:text-accent-foreground h-9 px-4 py-2 w-full text-left justify-start bg-muted hover:bg-muted">
                <svg width="15" height="15" viewBox="0 0 15 15" fill="none" xmlns="http://www.w3.org/2000/svg"
                  class="mr-2 h-4 w-4">
                  <path
                    d="M3 2.5C3 2.22386 3.22386 2 3.5 2H9.08579C9.21839 2 9.34557 2.05268 9.43934 2.14645L11.8536 4.56066C11.9473 4.65443 12 4.78161 12 4.91421V12.5C12 12.7761 11.7761 13 11.5 13H3.5C3.22386 13 3 12.7761 3 12.5V2.5ZM3.5 1C2.67157 1 2 1.67157 2 2.5V12.5C2 13.3284 2.67157 14 3.5 14H11.5C12.3284 14 13 13.3284 13 12.5V4.91421C13 4.51639 12.842 4.13486 12.5607 3.85355L10.1464 1.43934C9.86514 1.15804 9.48361 1 9.08579 1H3.5ZM4.5 4C4.22386 4 4 4.22386 4 4.5C4 4.77614 4.22386 5 4.5 5H7.5C7.77614 5 8 4.77614 8 4.5C8 4.22386 7.77614 4 7.5 4H4.5ZM4.5 7C4.22386 7 4 7.22386 4 7.5C4 7.77614 4.22386 8 4.5 8H10.5C10.7761 8 11 7.77614 11 7.5C11 7.22386 10.7761 7 10.5 7H4.5ZM4.5 10C4.22386 10 4 10.2239 4 10.5C4 10.7761 4.22386 11 4.5 11H10.5C10.7761 11 11 10.7761 11 10.5C11 10.2239 10.7761 10 10.5 10H4.5Z"
                    fill="currentColor" fill-rule="evenodd" clip-rule="evenodd"></path>
                </svg>
                我的假單
              </a>
              <a
                class="inline-flex items-center rounded-md text-sm font-medium transition-colors focus-visible:outline-none focus-visible:ring-1 focus-visible:ring-ring disabled:pointer-events-none disabled:opacity-50 text-primary hover:text-accent-foreground h-9 px-4 py-2 w-full text-left justify-start bg-muted hover:bg-muted">
                <svg width="15" height="15" viewBox="0 0 15 15" fill="none" xmlns="http://www.w3.org/2000/svg"
                  class="mr-2 h-4 w-4">
                  <path
                    d="M3 2.5C3 2.22386 3.22386 2 3.5 2H9.08579C9.21839 2 9.34557 2.05268 9.43934 2.14645L11.8536 4.56066C11.9473 4.65443 12 4.78161 12 4.91421V12.5C12 12.7761 11.7761 13 11.5 13H3.5C3.22386 13 3 12.7761 3 12.5V2.5ZM3.5 1C2.67157 1 2 1.67157 2 2.5V12.5C2 13.3284 2.67157 14 3.5 14H11.5C12.3284 14 13 13.3284 13 12.5V4.91421C13 4.51639 12.842 4.13486 12.5607 3.85355L10.1464 1.43934C9.86514 1.15804 9.48361 1 9.08579 1H3.5ZM4.5 4C4.22386 4 4 4.22386 4 4.5C4 4.77614 4.22386 5 4.5 5H7.5C7.77614 5 8 4.77614 8 4.5C8 4.22386 7.77614 4 7.5 4H4.5ZM4.5 7C4.22386 7 4 7.22386 4 7.5C4 7.77614 4.22386 8 4.5 8H10.5C10.7761 8 11 7.77614 11 7.5C11 7.22386 10.7761 7 10.5 7H4.5ZM4.5 10C4.22386 10 4 10.2239 4 10.5C4 10.7761 4.22386 11 4.5 11H10.5C10.7761 11 11 10.7761 11 10.5C11 10.2239 10.7761 10 10.5 10H4.5Z"
                    fill="currentColor" fill-rule="evenodd" clip-rule="evenodd"></path>
                </svg>
                簽核
              </a>
              <a
                class="inline-flex items-center rounded-md text-sm font-medium transition-colors focus-visible:outline-none focus-visible:ring-1 focus-visible:ring-ring disabled:pointer-events-none disabled:opacity-50 text-primary hover:text-accent-foreground h-9 px-4 py-2 w-full text-left justify-start bg-muted hover:bg-muted">
                <svg width="15" height="15" viewBox="0 0 15 15" fill="none" xmlns="http://www.w3.org/2000/svg"
                  class="mr-2 h-4 w-4">
                  <path
                    d="M3 2.5C3 2.22386 3.22386 2 3.5 2H9.08579C9.21839 2 9.34557 2.05268 9.43934 2.14645L11.8536 4.56066C11.9473 4.65443 12 4.78161 12 4.91421V12.5C12 12.7761 11.7761 13 11.5 13H3.5C3.22386 13 3 12.7761 3 12.5V2.5ZM3.5 1C2.67157 1 2 1.67157 2 2.5V12.5C2 13.3284 2.67157 14 3.5 14H11.5C12.3284 14 13 13.3284 13 12.5V4.91421C13 4.51639 12.842 4.13486 12.5607 3.85355L10.1464 1.43934C9.86514 1.15804 9.48361 1 9.08579 1H3.5ZM4.5 4C4.22386 4 4 4.22386 4 4.5C4 4.77614 4.22386 5 4.5 5H7.5C7.77614 5 8 4.77614 8 4.5C8 4.22386 7.77614 4 7.5 4H4.5ZM4.5 7C4.22386 7 4 7.22386 4 7.5C4 7.77614 4.22386 8 4.5 8H10.5C10.7761 8 11 7.77614 11 7.5C11 7.22386 10.7761 7 10.5 7H4.5ZM4.5 10C4.22386 10 4 10.2239 4 10.5C4 10.7761 4.22386 11 4.5 11H10.5C10.7761 11 11 10.7761 11 10.5C11 10.2239 10.7761 10 10.5 10H4.5Z"
                    fill="currentColor" fill-rule="evenodd" clip-rule="evenodd"></path>
                </svg>
                組織設定
              </a>
              <a
                class="inline-flex items-center rounded-md text-sm font-medium transition-colors focus-visible:outline-none focus-visible:ring-1 focus-visible:ring-ring disabled:pointer-events-none disabled:opacity-50 text-primary hover:text-accent-foreground h-9 px-4 py-2 w-full text-left justify-start bg-muted hover:bg-muted">
                <svg width="15" height="15" viewBox="0 0 15 15" fill="none" xmlns="http://www.w3.org/2000/svg"
                  class="mr-2 h-4 w-4">
                  <path
                    d="M7.07095 0.650238C6.67391 0.650238 6.32977 0.925096 6.24198 1.31231L6.0039 2.36247C5.6249 2.47269 5.26335 2.62363 4.92436 2.81013L4.01335 2.23585C3.67748 2.02413 3.23978 2.07312 2.95903 2.35386L2.35294 2.95996C2.0722 3.2407 2.0232 3.6784 2.23493 4.01427L2.80942 4.92561C2.62307 5.2645 2.47227 5.62594 2.36216 6.00481L1.31209 6.24287C0.924883 6.33065 0.650024 6.6748 0.650024 7.07183V7.92897C0.650024 8.32601 0.924883 8.67015 1.31209 8.75794L2.36228 8.99603C2.47246 9.375 2.62335 9.73652 2.80979 10.0755L2.2354 10.9867C2.02367 11.3225 2.07267 11.7602 2.35341 12.041L2.95951 12.6471C3.24025 12.9278 3.67795 12.9768 4.01382 12.7651L4.92506 12.1907C5.26384 12.377 5.62516 12.5278 6.0039 12.6379L6.24198 13.6881C6.32977 14.0753 6.67391 14.3502 7.07095 14.3502H7.92809C8.32512 14.3502 8.66927 14.0753 8.75705 13.6881L8.99505 12.6383C9.37411 12.5282 9.73573 12.3773 10.0748 12.1909L10.986 12.7653C11.3218 12.977 11.7595 12.928 12.0403 12.6473L12.6464 12.0412C12.9271 11.7604 12.9761 11.3227 12.7644 10.9869L12.1902 10.076C12.3768 9.73688 12.5278 9.37515 12.638 8.99596L13.6879 8.75794C14.0751 8.67015 14.35 8.32601 14.35 7.92897V7.07183C14.35 6.6748 14.0751 6.33065 13.6879 6.24287L12.6381 6.00488C12.528 5.62578 12.3771 5.26414 12.1906 4.92507L12.7648 4.01407C12.9766 3.6782 12.9276 3.2405 12.6468 2.95975L12.0407 2.35366C11.76 2.07292 11.3223 2.02392 10.9864 2.23565L10.0755 2.80989C9.73622 2.62328 9.37437 2.47229 8.99505 2.36209L8.75705 1.31231C8.66927 0.925096 8.32512 0.650238 7.92809 0.650238H7.07095ZM4.92053 3.81251C5.44724 3.44339 6.05665 3.18424 6.71543 3.06839L7.07095 1.50024H7.92809L8.28355 3.06816C8.94267 3.18387 9.5524 3.44302 10.0794 3.81224L11.4397 2.9547L12.0458 3.56079L11.1882 4.92117C11.5573 5.44798 11.8164 6.0575 11.9321 6.71638L13.5 7.07183V7.92897L11.932 8.28444C11.8162 8.94342 11.557 9.55301 11.1878 10.0798L12.0453 11.4402L11.4392 12.0462L10.0787 11.1886C9.55192 11.5576 8.94241 11.8166 8.28355 11.9323L7.92809 13.5002H7.07095L6.71543 11.932C6.0569 11.8162 5.44772 11.5572 4.92116 11.1883L3.56055 12.046L2.95445 11.4399L3.81213 10.0794C3.4431 9.55266 3.18403 8.94326 3.06825 8.2845L1.50002 7.92897V7.07183L3.06818 6.71632C3.18388 6.05765 3.44283 5.44833 3.81171 4.92165L2.95398 3.561L3.56008 2.95491L4.92053 3.81251ZM9.02496 7.50008C9.02496 8.34226 8.34223 9.02499 7.50005 9.02499C6.65786 9.02499 5.97513 8.34226 5.97513 7.50008C5.97513 6.65789 6.65786 5.97516 7.50005 5.97516C8.34223 5.97516 9.02496 6.65789 9.02496 7.50008ZM9.92496 7.50008C9.92496 8.83932 8.83929 9.92499 7.50005 9.92499C6.1608 9.92499 5.07513 8.83932 5.07513 7.50008C5.07513 6.16084 6.1608 5.07516 7.50005 5.07516C8.83929 5.07516 9.92496 6.16084 9.92496 7.50008Z"
                    fill="currentColor" fill-rule="evenodd" clip-rule="evenodd"></path>
                </svg>
                個人設定
              </a>
            </div>
          </div>
        </div>
        <div class="pt-[500px]">
          <div class="flex flex-col px-3">
            <div class="space-y-1">
              <a
                class="inline-flex items-center rounded-md text-sm font-medium transition-colors focus-visible:outline-none focus-visible:ring-1 focus-visible:ring-ring disabled:pointer-events-none disabled:opacity-50 text-primary hover:text-accent-foreground h-9 px-4 py-2 w-full text-left justify-start bg-muted hover:bg-muted">
                <svg width="24" height="24" viewBox="0 0 15 15" fill="none" xmlns="http://www.w3.org/2000/svg"
                  class="mr-2 h-4 w-4">
                  <path
                    d="M3 1C2.44771 1 2 1.44772 2 2V13C2 13.5523 2.44772 14 3 14H10.5C10.7761 14 11 13.7761 11 13.5C11 13.2239 10.7761 13 10.5 13H3V2L10.5 2C10.7761 2 11 1.77614 11 1.5C11 1.22386 10.7761 1 10.5 1H3ZM12.6036 4.89645C12.4083 4.70118 12.0917 4.70118 11.8964 4.89645C11.7012 5.09171 11.7012 5.40829 11.8964 5.60355L13.2929 7H6.5C6.22386 7 6 7.22386 6 7.5C6 7.77614 6.22386 8 6.5 8H13.2929L11.8964 9.39645C11.7012 9.59171 11.7012 9.90829 11.8964 10.1036C12.0917 10.2988 12.4083 10.2988 12.6036 10.1036L14.8536 7.85355C15.0488 7.65829 15.0488 7.34171 14.8536 7.14645L12.6036 4.89645Z"
                    fill="currentColor" fill-rule="evenodd" clip-rule="evenodd"></path>
                </svg>
                <p class="text-[16px]">登出</p>
              </a>
            </div>
          </div>
        </div>
      </div>
      <div class="col-span-4 lg:col-span lg:border-l">
        <div class="px-4 py-6 lg:px-8">
          <div class="flex">
            <Card class="w-[40%] mr-3" v-for="(index, key) in 3" :key="key">
              <CardHeader>
                <CardTitle v-if="index === 1">假單</CardTitle>
                <CardTitle v-else-if="index === 2">簽核</CardTitle>
                <CardTitle v-else>今日請假人員</CardTitle>
                <template v-if="index === 1">
                  <CardDescription>今日假單狀態</CardDescription>
                </template>
                <template v-if="index === 2">
                  <CardDescription>今日簽核狀態</CardDescription>
                </template>
                <template v-if="index === 3">
                  <CardDescription>今日請假人員資訊</CardDescription>
                </template>
              </CardHeader>
              <CardContent v-if="index === 1" class="h-[150px]">
                <div class="flex flex-col">
                  <p>簽合中 <Badge variant="destructive">1</Badge>
                  </p>
                  <p>已核准 <Badge>0</Badge>
                  </p>
                  <p>已退回 <Badge>0</Badge>
                  </p>
                </div>
              </CardContent>
              <CardContent v-if="index === 2" class="h-[150px]">
                <div class="flex flex-col">
                  <p>待簽核 <Badge variant="destructive">2</Badge>
                  </p>
                </div>
              </CardContent>
              <CardContent v-if="index === 3" class="h-[150px] overflow-y-scroll">
                <div class="flex flex-col">
                  <div class="flex items-center mb-2">
                    <Avatar class="mr-2">
                      <AvatarImage src="https://ui.shadcn.com/avatars/01.png" alt="@radix-vue" />
                      <AvatarFallback>B</AvatarFallback>
                    </Avatar>
                    <p>Bacon Su</p>
                  </div>
                  <div class="flex items-center mb-2">
                    <Avatar class="mr-2">
                      <AvatarImage src="https://ui.shadcn.com/avatars/02.png" alt="@radix-vue" />
                      <AvatarFallback>B</AvatarFallback>
                    </Avatar>
                    <p>Bacon Su</p>
                  </div>
                  <div class="flex items-center mb-2">
                    <Avatar class="mr-2">
                      <AvatarImage src="https://ui.shadcn.com/avatars/03.png" alt="@radix-vue" />
                      <AvatarFallback>B</AvatarFallback>
                    </Avatar>
                    <p>Bacon Su</p>
                  </div>
                  <div class="flex items-center mb-2">
                    <Avatar class="mr-2">
                      <AvatarImage src="https://ui.shadcn.com/avatars/04.png" alt="@radix-vue" />
                      <AvatarFallback>B</AvatarFallback>
                    </Avatar>
                    <p>Bacon Su</p>
                  </div>
                  <div class="flex items-center mb-2">
                    <Avatar class="mr-2">
                      <AvatarImage src="https://ui.shadcn.com/avatars/05.png" alt="@radix-vue" />
                      <AvatarFallback>B</AvatarFallback>
                    </Avatar>
                    <p>Bacon Su</p>
                  </div>
                </div>
              </CardContent>
              <CardFooter>
                <div class="flex justify-end">
                  <p class="mr-2">前往</p>
                  <svg width="24" height="24" viewBox="0 0 15 15" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path
                      d="M8.14645 3.14645C8.34171 2.95118 8.65829 2.95118 8.85355 3.14645L12.8536 7.14645C13.0488 7.34171 13.0488 7.65829 12.8536 7.85355L8.85355 11.8536C8.65829 12.0488 8.34171 12.0488 8.14645 11.8536C7.95118 11.6583 7.95118 11.3417 8.14645 11.1464L11.2929 8H2.5C2.22386 8 2 7.77614 2 7.5C2 7.22386 2.22386 7 2.5 7H11.2929L8.14645 3.85355C7.95118 3.65829 7.95118 3.34171 8.14645 3.14645Z"
                      fill="currentColor" fill-rule="evenodd" clip-rule="evenodd"></path>
                  </svg>
                </div>
              </CardFooter>
            </Card>
          </div>
          <div class="flex mt-[20px]">
            <Collapsible v-model:open="isOpen" class="w-[50%] space-y-2 border rounded-lg p-2 mr-3">
              <div class="flex items-center justify-between space-x-4 px-4">
                <h4 class="text-sm font-semibold text-primary">
                  今日假單
                </h4>
                <CollapsibleTrigger as-child>
                  <Button variant="secondary" size="sm" class="w-9 p-0">
                    <svg width="15" height="15" viewBox="0 0 15 15" fill="none" xmlns="http://www.w3.org/2000/svg">
                      <path
                        d="M7.5 2C7.77614 2 8 2.22386 8 2.5L8 11.2929L11.1464 8.14645C11.3417 7.95118 11.6583 7.95118 11.8536 8.14645C12.0488 8.34171 12.0488 8.65829 11.8536 8.85355L7.85355 12.8536C7.75979 12.9473 7.63261 13 7.5 13C7.36739 13 7.24021 12.9473 7.14645 12.8536L3.14645 8.85355C2.95118 8.65829 2.95118 8.34171 3.14645 8.14645C3.34171 7.95118 3.65829 7.95118 3.85355 8.14645L7 11.2929L7 2.5C7 2.22386 7.22386 2 7.5 2Z"
                        fill="currentColor" fill-rule="evenodd" clip-rule="evenodd"></path>
                    </svg>
                  </Button>
                </CollapsibleTrigger>
              </div>
              <div class="rounded-md border px-4 py-3 font-mono text-sm text-primary">
                <p>假單 2023-01-01</p>
              </div>
              <CollapsibleContent class="space-y-2">
                <div class="rounded-md px-4 py-3 font-mono text-sm text-primary">
                  <p>詳細內容</p>
                </div>
              </CollapsibleContent>
            </Collapsible>
            <Collapsible v-model:open="isOpen" class="w-[50%] space-y-2 border rounded-lg p-2">
              <div class="flex items-center justify-between space-x-4 px-4">
                <h4 class="text-sm font-semibold text-primary">
                  今日簽核
                </h4>
                <CollapsibleTrigger as-child>
                  <Button variant="secondary" size="sm" class="w-9 p-0">
                    <svg width="15" height="15" viewBox="0 0 15 15" fill="none" xmlns="http://www.w3.org/2000/svg">
                      <path
                        d="M7.5 2C7.77614 2 8 2.22386 8 2.5L8 11.2929L11.1464 8.14645C11.3417 7.95118 11.6583 7.95118 11.8536 8.14645C12.0488 8.34171 12.0488 8.65829 11.8536 8.85355L7.85355 12.8536C7.75979 12.9473 7.63261 13 7.5 13C7.36739 13 7.24021 12.9473 7.14645 12.8536L3.14645 8.85355C2.95118 8.65829 2.95118 8.34171 3.14645 8.14645C3.34171 7.95118 3.65829 7.95118 3.85355 8.14645L7 11.2929L7 2.5C7 2.22386 7.22386 2 7.5 2Z"
                        fill="currentColor" fill-rule="evenodd" clip-rule="evenodd"></path>
                    </svg>
                  </Button>
                </CollapsibleTrigger>
              </div>
              <div class="rounded-md border px-4 py-3 font-mono text-sm text-primary">
                <p>假單1</p>
              </div>
              <CollapsibleContent class="space-y-2">
                <div class="rounded-md px-4 py-3 font-mono text-sm text-primary">
                  <Button variant="secondary" size="sm" class="mr-3">通過</Button>
                  <Button variant="destructive" size="sm">退回</Button>
                </div>
              </CollapsibleContent>
              <div class="rounded-md border px-4 py-3 font-mono text-sm text-primary">
                <p>假單2</p>
              </div>
              <CollapsibleContent class="space-y-2">
                <div class="rounded-md px-4 py-3 font-mono text-sm text-primary">
                  <Button variant="secondary" size="sm" class="mr-3">通過</Button>
                  <Button variant="destructive" size="sm">退回</Button>
                </div>
              </CollapsibleContent>
            </Collapsible>
          </div>
          <div dir="ltr" data-orientation="horizontal" class="h-full space-y-6">
            <div data-orientation="horizontal" role="none" class="shrink-0 bg-border h-[1px] w-full my-4"></div>
            <div class="relative">
              <div dir="ltr" class="relative"
                style="position: relative; --radix-scroll-area-corner-width:0px; --radix-scroll-area-corner-height:0px;">
                <div data-radix-scroll-area-viewport class="h-full w-full rounded-[inherit]" style="overflow: scroll;">
                  <div style="min-width: 100%; display: table;">
                    <div class="flex space-x-4 pb-4">
                      <div class="space-y-3 w-[250px]">
                        <span data-state="closed">
                          <div class="overflow-hidden rounded-md">
                            <div class="text-secondary-foreground h-[200px]">
                              <p>辦公室消毒清潔</p>
                              <div class="h-[100px] p-2">
                                <p class="">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Nesciunt, eaque
                                  totam! Autem earum illum officiis sapiente maxime, vitae reiciendis animi eos. Omnis
                                  iure labore fugiat inventore minus beatae hic sint.</p>
                              </div>
                            </div>
                          </div>
                        </span>
                        <div class="space-y-1 text-sm">
                          <h3 class="font-medium leading-none text-primary">開發一部</h3>
                          <p class="text-xs text-muted-foreground">2023-09-20</p>
                        </div>
                      </div>
                      <div class="space-y-3 w-[250px]">
                        <span data-state="closed">
                          <div class="overflow-hidden rounded-md">
                            <div class="text-secondary-foreground h-[200px]">
                              <p>公用資料夾恢復</p>
                              <div class="h-[100px] p-2">
                                <p class="">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Nesciunt, eaque
                                  totam! Autem earum illum officiis sapiente maxime, vitae reiciendis animi eos. Omnis
                                  iure labore fugiat inventore minus beatae hic sint.</p>
                              </div>
                            </div>
                          </div>
                        </span>
                        <div class="space-y-1 text-sm">
                          <h3 class="font-medium leading-none text-primary">開發二部</h3>
                          <p class="text-xs text-muted-foreground">2023-09-19</p>
                        </div>
                      </div>
                      <div class="space-y-3 w-[250px]">
                        <span data-state="closed">
                          <div class="overflow-hidden rounded-md">
                            <div class="text-secondary-foreground h-[200px]">
                              <p>定期備份個人資料</p>
                              <div class="h-[100px] p-2">
                                <p class="">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Nesciunt, eaque
                                  totam! Autem earum illum officiis sapiente maxime, vitae reiciendis animi eos. Omnis
                                  iure labore fugiat inventore minus beatae hic sint.</p>
                              </div>
                            </div>
                          </div>
                        </span>
                        <div class="space-y-1 text-sm">
                          <h3 class="font-medium leading-none text-primary">前端開發部</h3>
                          <p class="text-xs text-muted-foreground">2023-09-18</p>
                        </div>
                      </div>
                      <div class="space-y-3 w-[250px]">
                        <span data-state="closed">
                          <div class="overflow-hidden rounded-md">
                            <div class="text-secondary-foreground h-[200px]">
                              <p>辦公室消毒清潔</p>
                              <div class="h-[100px] p-2">
                                <p class="">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Nesciunt, eaque
                                  totam! Autem earum illum officiis sapiente maxime, vitae reiciendis animi eos. Omnis
                                  iure labore fugiat inventore minus beatae hic sint.</p>
                              </div>
                            </div>
                          </div>
                        </span>
                        <div class="space-y-1 text-sm">
                          <h3 class="font-medium leading-none text-primary">專案部</h3>
                          <p class="text-xs text-muted-foreground">2023-09-18</p>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.layout-container {
  min-height: 100vh;
  max-width: 1440px;
  @apply mx-auto;
}
</style>