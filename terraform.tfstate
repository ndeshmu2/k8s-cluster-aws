provider "aws" {
    region = "us-east-1"
}

resource "aws_vpc" "main"{
    cidr_block = "10.0.0.0/16"
}

resource "aws_subnet" "main" {

    vpc_id      = aws_vpc.main.id
    cidr_block  = "10.0.1.0/24"
    availability_zone = "us-east-1a"

}

resource "aws_instance" "openshift_node" {
    ami           = "ami-0d7a109bf30624c99"
    instance_type = "t2.micro"
    subnet_id     = aws_subnet.main.id

    tags = {
        Name = "OpenShiftNode"
    }
}

