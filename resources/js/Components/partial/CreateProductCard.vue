<script setup lang="ts">
    import { useForm } from 'vee-validate'
    import { toTypedSchema } from '@vee-validate/zod'
    import * as z from 'zod'

    import {
    Card,
    CardContent,
    CardDescription,
    CardFooter,
    CardHeader,
    CardTitle,
    } from '@/Components/ui/card'
    
    import {
    Select,
    SelectContent,
    SelectItem,
    SelectTrigger,
    SelectValue,
    } from '@/Components/ui/select'

    import {
        FormControl,
        FormDescription,
        FormField,
        FormItem,
        FormLabel,
        FormMessage,
        } from '@/Components/ui/form'
    
    import { Button } from '@/Components/ui/button'
    import { Input } from '@/Components/ui/input'
    // import { Label } from '@/Components/ui/label'

    const formSchema = toTypedSchema(z.object({
        username: z.string().min(2).max(50),
    }))
    const form = useForm({
        validationSchema: formSchema,
    })
    const onSubmit = form.handleSubmit((values) => {
        console.log('Form submitted!', values)
    })
</script>
<template>
    <Card>
        <CardHeader>
            <CardTitle>New Product</CardTitle>
            <CardDescription>Fill this following form</CardDescription>
        </CardHeader>
        <CardContent>
            <form class="w-3/3 space-y-6" @submit="onSubmit">
                <FormField name="name">
                    <FormItem>
                        <FormLabel>Name</FormLabel>
                        <FormControl>
                            <Input type="text" placeholder="shadcn"  />
                        </FormControl>
                        <FormDescription>
                            This is your product display name.
                        </FormDescription>
                        <FormMessage />
                    </FormItem>
                </FormField>
                <Button type="submit">
                    Submit
                </Button>
            </form>
        </CardContent>
        <CardFooter>
            
        </CardFooter>
    </Card>
</template>